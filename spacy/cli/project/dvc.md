Module spacy.cli.project.dvc
============================
This module contains helpers and subcommands for integrating spaCy projects
with Data Version Controk (DVC). https://dvc.org

Functions
---------

    
`check_workflows(workflows: List[str], workflow: Optional[str] = None) ‑> None`
:   Validate workflows provided in project.yml and check that a given
    workflow can be used to generate a DVC config.
    
    workflows (List[str]): Names of the available workflows.
    workflow (Optional[str]): The name of the workflow to convert.

    
`ensure_dvc(project_dir: pathlib.Path) ‑> None`
:   Ensure that the "dvc" command is available and that the current project
    directory is an initialized DVC project.

    
`project_update_dvc(project_dir: pathlib.Path, workflow: Optional[str] = None, *, verbose: bool = False, force: bool = False) ‑> None`
:   Update the auto-generated Data Version Control (DVC) config file. A DVC
    project can only define one pipeline, so you need to specify one workflow
    defined in the project.yml. Will only update the file if the checksum changed.
    
    project_dir (Path): The project directory.
    workflow (Optional[str]): Optional name of workflow defined in project.yml.
        If not set, the first workflow will be used.
    verbose (bool): Print more info.
    force (bool): Force update DVC config.

    
`project_update_dvc_cli(project_dir: pathlib.Path = <typer.models.ArgumentInfo object>, workflow: Optional[str] = <typer.models.ArgumentInfo object>, verbose: bool = <typer.models.OptionInfo object>, force: bool = <typer.models.OptionInfo object>)`
:   Auto-generate Data Version Control (DVC) config. A DVC
    project can only define one pipeline, so you need to specify one workflow
    defined in the project.yml. If no workflow is specified, the first defined
    workflow is used. The DVC config will only be updated if the project.yml
    changed.
    
    DOCS: https://spacy.io/api/cli#project-dvc

    
`run_dvc_commands(commands: Iterable[str] = [], flags: Dict[str, bool] = {}) ‑> None`
:   Run a sequence of DVC commands in a subprocess, in order.
    
    commands (List[str]): The string commands without the leading "dvc".
    flags (Dict[str, bool]): Conditional flags to be added to command. Makes it
        easier to pass flags like --quiet that depend on a variable or
        command-line setting while avoiding lots of nested conditionals.

    
`update_dvc_config(path: pathlib.Path, config: Dict[str, Any], workflow: Optional[str] = None, verbose: bool = False, silent: bool = False, force: bool = False) ‑> bool`
:   Re-run the DVC commands in dry mode and update dvc.yaml file in the
    project directory. The file is auto-generated based on the config. The
    first line of the auto-generated file specifies the hash of the config
    dict, so if any of the config values change, the DVC config is regenerated.
    
    path (Path): The path to the project directory.
    config (Dict[str, Any]): The loaded project.yml.
    verbose (bool): Whether to print additional info (via DVC).
    silent (bool): Don't output anything (via DVC).
    force (bool): Force update, even if hashes match.
    RETURNS (bool): Whether the DVC config file was updated.