Module spacy.cli.download
=========================

Functions
---------

    
`download(model: str, direct: bool = False, sdist: bool = False, *pip_args) ‑> None`
:   

    
`download_cli(ctx: typer.models.Context, model: str = <typer.models.ArgumentInfo object>, direct: bool = <typer.models.OptionInfo object>, sdist: bool = <typer.models.OptionInfo object>)`
:   Download compatible trained pipeline from the default download path using
    pip. If --direct flag is set, the command expects the full package name with
    version. For direct downloads, the compatibility check will be skipped. All
    additional arguments provided to this command will be passed to `pip install`
    on package installation.
    
    DOCS: https://spacy.io/api/cli#download
    AVAILABLE PACKAGES: https://spacy.io/models

    
`download_model(filename: str, user_pip_args: Optional[Sequence[str]] = None) ‑> None`
:   

    
`get_compatibility() ‑> dict`
:   

    
`get_version(model: str, comp: dict) ‑> str`
: