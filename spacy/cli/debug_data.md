Module spacy.cli.debug_data
===========================

Functions
---------

    
`debug_data(config_path: pathlib.Path, *, config_overrides: Dict[str, Any] = {}, ignore_warnings: bool = False, verbose: bool = False, no_format: bool = True, silent: bool = True)`
:   

    
`debug_data_cli(ctx: typer.models.Context, config_path: pathlib.Path = <typer.models.ArgumentInfo object>, code_path: Optional[pathlib.Path] = <typer.models.OptionInfo object>, ignore_warnings: bool = <typer.models.OptionInfo object>, verbose: bool = <typer.models.OptionInfo object>, no_format: bool = <typer.models.OptionInfo object>)`
:   Analyze, debug and validate your training and development data. Outputs
    useful stats, and can help you find problems like invalid entity annotations,
    cyclic dependencies, low data labels and more.
    
    DOCS: https://spacy.io/api/cli#debug-data