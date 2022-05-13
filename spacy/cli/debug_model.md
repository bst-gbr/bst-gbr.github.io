Module spacy.cli.debug_model
============================

Functions
---------

    
`debug_model(config, resolved_train_config, nlp, pipe, *, print_settings: Optional[Dict[str, Any]] = None)`
:   

    
`debug_model_cli(ctx: typer.models.Context, config_path: pathlib.Path = <typer.models.ArgumentInfo object>, component: str = <typer.models.ArgumentInfo object>, layers: str = <typer.models.OptionInfo object>, dimensions: bool = <typer.models.OptionInfo object>, parameters: bool = <typer.models.OptionInfo object>, gradients: bool = <typer.models.OptionInfo object>, attributes: bool = <typer.models.OptionInfo object>, P0: bool = <typer.models.OptionInfo object>, P1: bool = <typer.models.OptionInfo object>, P2: bool = <typer.models.OptionInfo object>, P3: bool = <typer.models.OptionInfo object>, use_gpu: int = <typer.models.OptionInfo object>)`
:   Analyze a Thinc model implementation. Includes checks for internal structure
    and activations during training.
    
    DOCS: https://spacy.io/api/cli#debug-model