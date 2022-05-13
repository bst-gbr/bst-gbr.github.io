Module spacy.cli.project.pull
=============================

Functions
---------

    
`project_pull(project_dir: pathlib.Path, remote: str, *, verbose: bool = False)`
:   

    
`project_pull_cli(remote: str = <typer.models.ArgumentInfo object>, project_dir: pathlib.Path = <typer.models.ArgumentInfo object>)`
:   Retrieve available precomputed outputs from a remote storage.
    You can alias remotes in your project.yml by mapping them to storage paths.
    A storage can be anything that the smart-open library can upload to, e.g.
    AWS, Google Cloud Storage, SSH, local directories etc.
    
    DOCS: https://spacy.io/api/cli#project-pull