Module spacy.cli.debug_config
=============================

Functions
---------

    
`debug_config(config_path: pathlib.Path, *, overrides: Dict[str, Any] = {}, show_funcs: bool = False, show_vars: bool = False)`
:   

    
`debug_config_cli(ctx: typer.models.Context, config_path: pathlib.Path = <typer.models.ArgumentInfo object>, code_path: Optional[pathlib.Path] = <typer.models.OptionInfo object>, show_funcs: bool = <typer.models.OptionInfo object>, show_vars: bool = <typer.models.OptionInfo object>)`
:   Debug a config file and show validation errors. The command will
    create all objects in the tree and validate them. Note that some config
    validation errors are blocking and will prevent the rest of the config from
    being resolved. This means that you may not see all validation errors at
    once and some issues are only shown once previous errors have been fixed.
    Similar as with the 'train' command, you can override settings from the config
    as command line options. For instance, --training.batch_size 128 overrides
    the value of "batch_size" in the block "[training]".
    
    DOCS: https://spacy.io/api/cli#debug-config

    
`get_registered_funcs(config: thinc.config.Config) ‑> List[Dict[str, Union[str, int, None]]]`
:   

    
`get_variables(config: thinc.config.Config) ‑> Dict[str, Any]`
: