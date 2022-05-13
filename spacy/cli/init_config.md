Module spacy.cli.init_config
============================

Functions
---------

    
`fill_config(output_file: pathlib.Path, base_path: pathlib.Path, *, pretraining: bool = False, diff: bool = False, silent: bool = False) ‑> Tuple[thinc.config.Config, thinc.config.Config]`
:   

    
`has_spacy_transformers() ‑> bool`
:   

    
`init_config(*, lang: str, pipeline: List[str], optimize: str, gpu: bool, pretraining: bool = False, silent: bool = True) ‑> thinc.config.Config`
:   

    
`init_config_cli(output_file: pathlib.Path = <typer.models.ArgumentInfo object>, lang: str = <typer.models.OptionInfo object>, pipeline: str = <typer.models.OptionInfo object>, optimize: spacy.cli.init_config.Optimizations = <typer.models.OptionInfo object>, gpu: bool = <typer.models.OptionInfo object>, pretraining: bool = <typer.models.OptionInfo object>, force_overwrite: bool = <typer.models.OptionInfo object>)`
:   Generate a starter config file for training. Based on your requirements
    specified via the CLI arguments, this command generates a config with the
    optimal settings for your use case. This includes the choice of architecture,
    pretrained weights and related hyperparameters.
    
    DOCS: https://spacy.io/api/cli#init-config

    
`init_fill_config_cli(base_path: pathlib.Path = <typer.models.ArgumentInfo object>, output_file: pathlib.Path = <typer.models.ArgumentInfo object>, pretraining: bool = <typer.models.OptionInfo object>, diff: bool = <typer.models.OptionInfo object>, code_path: Optional[pathlib.Path] = <typer.models.OptionInfo object>)`
:   Fill partial config file with default values. Will add all missing settings
    from the default config and will create all objects, check the registered
    functions for their default values and update the base config. This command
    can be used with a config generated via the training quickstart widget:
    https://spacy.io/usage/training#quickstart
    
    DOCS: https://spacy.io/api/cli#init-fill-config

    
`save_config(config: thinc.config.Config, output_file: pathlib.Path, is_stdout: bool = False, silent: bool = False) ‑> None`
:   

    
`validate_config_for_pretrain(config: thinc.config.Config, msg: wasabi.printer.Printer) ‑> None`
:   

Classes
-------

`Optimizations(value, names=None, *, module=None, qualname=None, type=None, start=1)`
:   An enumeration.

    ### Ancestors (in MRO)

    * builtins.str
    * enum.Enum

    ### Class variables

    `accuracy`
    :

    `efficiency`
    :