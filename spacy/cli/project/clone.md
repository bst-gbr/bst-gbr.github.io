Module spacy.cli.project.clone
==============================

Functions
---------

    
`check_clone(name: str, dest: pathlib.Path, repo: str) ‑> None`
:   Check and validate that the destination path can be used to clone. Will
    check that Git is available and that the destination path is suitable.
    
    name (str): Name of the directory to clone from the repo.
    dest (Path): Local destination of cloned directory.
    repo (str): URL of the repo to clone from.

    
`project_clone(name: str, dest: pathlib.Path, *, repo: str = 'https://github.com/explosion/projects', branch: str = 'v3', sparse_checkout: bool = False) ‑> None`
:   Clone a project template from a repository.
    
    name (str): Name of subdirectory to clone.
    dest (Path): Destination path of cloned project.
    repo (str): URL of Git repo containing project templates.
    branch (str): The branch to clone from

    
`project_clone_cli(name: str = <typer.models.ArgumentInfo object>, dest: Optional[pathlib.Path] = <typer.models.ArgumentInfo object>, repo: str = <typer.models.OptionInfo object>, branch: Optional[str] = <typer.models.OptionInfo object>, sparse_checkout: bool = <typer.models.OptionInfo object>)`
:   Clone a project template from a repository. Calls into "git" and will
    only download the files from the given subdirectory. The GitHub repo
    defaults to the official spaCy template repo, but can be customized
    (including using a private repo).
    
    DOCS: https://spacy.io/api/cli#project-clone