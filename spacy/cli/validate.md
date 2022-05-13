Module spacy.cli.validate
=========================

Functions
---------

    
`get_model_pkgs(silent: bool = False) ‑> Tuple[dict, dict]`
:   

    
`reformat_version(version: str) ‑> str`
:   Hack to reformat old versions ending on '-alpha' to match pip format.

    
`validate() ‑> None`
:   

    
`validate_cli()`
:   Validate the currently installed pipeline packages and spaCy version. Checks
    if the installed packages are compatible and shows upgrade instructions if
    available. Should be run after `pip install -U spacy`.
    
    DOCS: https://spacy.io/api/cli#validate