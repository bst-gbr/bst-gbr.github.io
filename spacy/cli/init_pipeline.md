Module spacy.cli.init_pipeline
==============================

Functions
---------

    
`init_labels_cli(ctx: typer.models.Context, config_path: pathlib.Path = <typer.models.ArgumentInfo object>, output_path: pathlib.Path = <typer.models.ArgumentInfo object>, code_path: Optional[pathlib.Path] = <typer.models.OptionInfo object>, verbose: bool = <typer.models.OptionInfo object>, use_gpu: int = <typer.models.OptionInfo object>)`
:   Generate JSON files for the labels in the data. This helps speed up the
    training process, since spaCy won't have to preprocess the data to
    extract the labels.

    
`init_pipeline_cli(ctx: typer.models.Context, config_path: pathlib.Path = <typer.models.ArgumentInfo object>, output_path: pathlib.Path = <typer.models.ArgumentInfo object>, code_path: Optional[pathlib.Path] = <typer.models.OptionInfo object>, verbose: bool = <typer.models.OptionInfo object>, use_gpu: int = <typer.models.OptionInfo object>)`
:   

    
`init_vectors_cli(lang: str = <typer.models.ArgumentInfo object>, vectors_loc: pathlib.Path = <typer.models.ArgumentInfo object>, output_dir: pathlib.Path = <typer.models.ArgumentInfo object>, prune: int = <typer.models.OptionInfo object>, truncate: int = <typer.models.OptionInfo object>, mode: str = <typer.models.OptionInfo object>, name: Optional[str] = <typer.models.OptionInfo object>, verbose: bool = <typer.models.OptionInfo object>, jsonl_loc: Optional[pathlib.Path] = <typer.models.OptionInfo object>)`
:   Convert word vectors for use with spaCy. Will export an nlp object that
    you can use in the [initialize] block of your config to initialize
    a model with vectors.

    
`update_lexemes(nlp: spacy.language.Language, jsonl_loc: pathlib.Path) ‑> None`
: