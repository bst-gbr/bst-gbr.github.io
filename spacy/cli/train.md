Module spacy.cli.train
======================

Functions
---------

    
`train(config_path: Union[str, pathlib.Path], output_path: Union[str, pathlib.Path, None] = None, *, use_gpu: int = -1, overrides: Dict[str, Any] = {})`
:   

    
`train_cli(ctx: typer.models.Context, config_path: pathlib.Path = <typer.models.ArgumentInfo object>, output_path: Optional[pathlib.Path] = <typer.models.OptionInfo object>, code_path: Optional[pathlib.Path] = <typer.models.OptionInfo object>, verbose: bool = <typer.models.OptionInfo object>, use_gpu: int = <typer.models.OptionInfo object>)`
:   Train or update a spaCy pipeline. Requires data in spaCy's binary format. To
    convert data from other formats, use the `spacy convert` command. The
    config file includes all settings and hyperparameters used during training.
    To override settings in the config, e.g. settings that point to local
    paths or that you want to experiment with, you can override them as
    command line options. For instance, --training.batch_size 128 overrides
    the value of "batch_size" in the block "[training]". The --code argument
    lets you pass in a Python file that's imported before training. It can be
    used to register custom functions and architectures that can then be
    referenced in the config.
    
    DOCS: https://spacy.io/api/cli#train