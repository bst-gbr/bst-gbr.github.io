Module spacy.cli.info
=====================

Functions
---------

    
`get_markdown(data: Dict[str, Any], title: Optional[str] = None, exclude: Optional[List[str]] = None) ‑> str`
:   Get data in GitHub-flavoured Markdown format for issues etc.
    
    data (Dict[str, Any]): Label/value pairs.
    title (str): Optional title, will be rendered as headline 2.
    exclude (List[str]): Names of keys to exclude.
    RETURNS (str): The Markdown string.

    
`info(model: Optional[str] = None, *, markdown: bool = False, silent: bool = True, exclude: Optional[List[str]] = None) ‑> Union[str, dict]`
:   

    
`info_cli(model: Optional[str] = <typer.models.ArgumentInfo object>, markdown: bool = <typer.models.OptionInfo object>, silent: bool = <typer.models.OptionInfo object>, exclude: str = <typer.models.OptionInfo object>)`
:   Print info about spaCy installation. If a pipeline is specified as an argument,
    print its meta information. Flag --markdown prints details in Markdown for easy
    copy-pasting to GitHub issues.
    
    DOCS: https://spacy.io/api/cli#info

    
`info_model(model: str, *, silent: bool = True) ‑> Dict[str, Any]`
:   Generate info about a specific model.
    
    model (str): Model name of path.
    silent (bool): Don't print anything, just return.
    RETURNS (dict): The model meta.

    
`info_spacy() ‑> Dict[str, Any]`
:   Generate info about the current spaCy intallation.
    
    RETURNS (dict): The spaCy info.