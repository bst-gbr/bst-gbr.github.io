Module spacy.cli.project.assets
===============================

Functions
---------

    
`check_private_asset(dest: pathlib.Path, checksum: Optional[str] = None) ‑> None`
:   Check and validate assets without a URL (private assets that the user
    has to provide themselves) and give feedback about the checksum.
    
    dest (Path): Destination path of the asset.
    checksum (Optional[str]): Optional checksum of the expected file.

    
`convert_asset_url(url: str) ‑> str`
:   Check and convert the asset URL if needed.
    
    url (str): The asset URL.
    RETURNS (str): The converted URL.

    
`fetch_asset(project_path: pathlib.Path, url: str, dest: pathlib.Path, checksum: Optional[str] = None) ‑> None`
:   Fetch an asset from a given URL or path. If a checksum is provided and a
    local file exists, it's only re-downloaded if the checksum doesn't match.
    
    project_path (Path): Path to project directory.
    url (str): URL or path to asset.
    checksum (Optional[str]): Optional expected checksum of local file.
    RETURNS (Optional[Path]): The path to the fetched asset or None if fetching
        the asset failed.

    
`project_assets(project_dir: pathlib.Path, *, overrides: Dict[str, Any] = {}, sparse_checkout: bool = False) ‑> None`
:   Fetch assets for a project using DVC if possible.
    
    project_dir (Path): Path to project directory.

    
`project_assets_cli(ctx: typer.models.Context, project_dir: pathlib.Path = <typer.models.ArgumentInfo object>, sparse_checkout: bool = <typer.models.OptionInfo object>)`
:   Fetch project assets like datasets and pretrained weights. Assets are
    defined in the "assets" section of the project.yml. If a checksum is
    provided in the project.yml, the file is only downloaded if no local file
    with the same checksum exists.
    
    DOCS: https://spacy.io/api/cli#project-assets