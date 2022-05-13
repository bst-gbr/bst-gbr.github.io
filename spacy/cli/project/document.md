Module spacy.cli.project.document
=================================

Functions
---------

    
`project_document(project_dir: pathlib.Path, output_file: pathlib.Path, *, no_emoji: bool = False) ‑> None`
:   

    
`project_document_cli(project_dir: pathlib.Path = <typer.models.ArgumentInfo object>, output_file: pathlib.Path = <typer.models.OptionInfo object>, no_emoji: bool = <typer.models.OptionInfo object>)`
:   Auto-generate a README.md for a project. If the content is saved to a file,
    hidden markers are added so you can add custom content before or after the
    auto-generated section and only the auto-generated docs will be replaced
    when you re-run the command.
    
    DOCS: https://spacy.io/api/cli#project-document