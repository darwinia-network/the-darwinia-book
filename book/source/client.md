# client
> [darwinia/bin/client][0]

## `darwinia/bin/client/cli`

Parse command line interface arguments and prepares the command for execution.

Before returning, this function performs various initializations, such as initializing the panic handler and the logger, or increasing the limit for file descriptors.

### Remarks

`CC` is a custom subcommand. This needs to be an `enum`! If no custom subcommand is required, `NoCustom` can be used as type here.

`RP` are custom parameters for the run command. This needs to be a `struct`! The custom parameters are visible to the user as if they were normal run command parameters. If no custom parameters are required, `NoCustom` can be used as type here.

```rust
pub fn parse_and_prepare<'a, CC, RP, I>(
	version: &'a VersionInfo,
	impl_name: &'static str,
	args: I,
) -> ParseAndPrepare<'a, CC, RP>
where
	CC: StructOpt + Clone + GetSharedParams,
	RP: StructOpt + Clone + StructOptInternal,
	I: IntoIterator,
	<I as IntoIterator>::Item: Into<std::ffi::OsString> + Clone,
{
	let full_version = sc_service::config::full_version_from_strs(version.version, version.commit);

	sp_panic_handler::set(version.support_url, &full_version);
	let matches = CoreParams::<CC, RP>::clap()
		.name(version.executable_name)
		.author(version.author)
		.about(version.description)
		.version(&(full_version + "\n")[..])
		.setting(AppSettings::GlobalVersion)
		.setting(AppSettings::ArgsNegateSubcommands)
		.setting(AppSettings::SubcommandsNegateReqs)
		.get_matches_from(args);
	let cli_args = CoreParams::<CC, RP>::from_clap(&matches);
	fdlimit::raise_fd_limit();

	let args = match cli_args {
		params::CoreParams::Run(params) => ParseAndPrepare::Run(ParseAndPrepareRun {
			params,
			impl_name,
			version,
		}),
		params::CoreParams::BuildSpec(params) => {
			ParseAndPrepare::BuildSpec(ParseAndPrepareBuildSpec { params, version })
		}
		params::CoreParams::ExportBlocks(params) => {
			ParseAndPrepare::ExportBlocks(ParseAndPrepareExport { params, version })
		}
		params::CoreParams::ImportBlocks(params) => {
			ParseAndPrepare::ImportBlocks(ParseAndPrepareImport { params, version })
		}
		params::CoreParams::CheckBlock(params) => ParseAndPrepare::CheckBlock(CheckBlock { params, version }),
		params::CoreParams::PurgeChain(params) => ParseAndPrepare::PurgeChain(ParseAndPreparePurge { params, version }),
		params::CoreParams::Revert(params) => ParseAndPrepare::RevertChain(ParseAndPrepareRevert { params, version }),
		params::CoreParams::Custom(params) => ParseAndPrepare::CustomCommand(params),
	};
	init_logger(
		args.shared_params()
			.and_then(|p| p.log.as_ref())
			.map(|v| v.as_ref())
			.unwrap_or(""),
	);
	args
}
```

[0]: https://github.com/darwinia-network/darwinia/tree/develop/bin
