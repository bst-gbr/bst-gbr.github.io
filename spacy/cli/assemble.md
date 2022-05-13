Module spacy.cli.assemble
=========================

Functions
---------

    
`assemble_cli(ctx: typer.models.Context, config_path: pathlib.Path = <typer.models.ArgumentInfo object>, output_path: pathlib.Path = <typer.models.ArgumentInfo object>, code_path: Optional[pathlib.Path] = <typer.models.OptionInfo object>, verbose: bool = <typer.models.OptionInfo object>)`
:   Assemble a spaCy pipeline from a config file. The config file includes
    all settings for initializing the pipeline. To override settings in the
    config, e.g. settings that point to local paths or that you want to
    experiment with, you can override them as command line options. The
    --code argument lets you pass in a Python file that can be used to
    register custom functions that are referenced in the config.
    
    DOCS: https://spacy.io/api/cli#assemble