Module spacy.cli.package
========================

Functions
---------

    
`create_file(file_path: pathlib.Path, contents: str) ‑> None`
:   

    
`generate_meta(existing_meta: Dict[str, Any], msg: wasabi.printer.Printer) ‑> Dict[str, Any]`
:   

    
`generate_readme(meta: Dict[str, Any]) ‑> str`
:   Generate a Markdown-formatted README text from a model meta.json. Used
    within the GitHub release notes and as content for README.md file added
    to model packages.

    
`get_build_formats(formats: List[str]) ‑> Tuple[bool, bool]`
:   

    
`get_meta(model_path: Union[str, pathlib.Path], existing_meta: Dict[str, Any]) ‑> Dict[str, Any]`
:   

    
`get_third_party_dependencies(config: thinc.config.Config, exclude: List[str] = []) ‑> List[str]`
:   If the config includes references to registered functions that are
    provided by third-party packages (spacy-transformers, other libraries), we
    want to include them in meta["requirements"] so that the package specifies
    them as dependencies and the user won't have to do it manually.
    
    We do this by:
    - traversing the config to check for registered function (@ keys)
    - looking up the functions and getting their module
    - looking up the module version and generating an appropriate version range
    
    config (Config): The pipeline config.
    exclude (list): List of packages to exclude (e.g. that already exist in meta).
    RETURNS (list): The versioned requirements.

    
`has_wheel() ‑> bool`
:   

    
`package(input_dir: pathlib.Path, output_dir: pathlib.Path, meta_path: Optional[pathlib.Path] = None, code_paths: List[pathlib.Path] = [], name: Optional[str] = None, version: Optional[str] = None, create_meta: bool = False, create_sdist: bool = True, create_wheel: bool = False, force: bool = False, silent: bool = True) ‑> None`
:   

    
`package_cli(input_dir: pathlib.Path = <typer.models.ArgumentInfo object>, output_dir: pathlib.Path = <typer.models.ArgumentInfo object>, code_paths: str = <typer.models.OptionInfo object>, meta_path: Optional[pathlib.Path] = <typer.models.OptionInfo object>, create_meta: bool = <typer.models.OptionInfo object>, name: Optional[str] = <typer.models.OptionInfo object>, version: Optional[str] = <typer.models.OptionInfo object>, build: str = <typer.models.OptionInfo object>, force: bool = <typer.models.OptionInfo object>)`
:   Generate an installable Python package for a pipeline. Includes binary data,
    meta and required installation files. A new directory will be created in the
    specified output directory, and the data will be copied over. If
    --create-meta is set and a meta.json already exists in the output directory,
    the existing values will be used as the defaults in the command-line prompt.
    After packaging, "python setup.py sdist" is run in the package directory,
    which will create a .tar.gz archive that can be installed via "pip install".
    
    If additional code files are provided (e.g. Python files containing custom
    registered functions like pipeline components), they are copied into the
    package and imported in the __init__.py.
    
    DOCS: https://spacy.io/api/cli#package