Module spacy.cli.project.push
=============================

Functions
---------

    
`project_push(project_dir: pathlib.Path, remote: str)`
:   Persist outputs to a remote storage. You can alias remotes in your project.yml
    by mapping them to storage paths. A storage can be anything that the smart-open
    library can upload to, e.g. gcs, aws, ssh, local directories etc

    
`project_push_cli(remote: str = <typer.models.ArgumentInfo object>, project_dir: pathlib.Path = <typer.models.ArgumentInfo object>)`
:   Persist outputs to a remote storage. You can alias remotes in your
    project.yml by mapping them to storage paths. A storage can be anything that
    the smart-open library can upload to, e.g. AWS, Google Cloud Storage, SSH,
    local directories etc.
    
    DOCS: https://spacy.io/api/cli#project-push