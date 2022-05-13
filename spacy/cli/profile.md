Module spacy.cli.profile
========================

Functions
---------

    
`parse_texts(nlp: spacy.language.Language, texts: Sequence[str]) ‑> None`
:   

    
`profile(model: str, inputs: Optional[pathlib.Path] = None, n_texts: int = 10000) ‑> None`
:   

    
`profile_cli(ctx: typer.models.Context, model: str = <typer.models.ArgumentInfo object>, inputs: Optional[pathlib.Path] = <typer.models.ArgumentInfo object>, n_texts: int = <typer.models.OptionInfo object>)`
:   Profile which functions take the most time in a spaCy pipeline.
    Input should be formatted as one JSON object per line with a key "text".
    It can either be provided as a JSONL file, or be read from sys.sytdin.
    If no input file is specified, the IMDB dataset is loaded via Thinc.
    
    DOCS: https://spacy.io/api/cli#debug-profile