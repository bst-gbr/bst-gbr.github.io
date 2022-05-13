Module spacy.cli.convert
========================

Functions
---------

    
`autodetect_ner_format(input_data: str) ‑> Optional[str]`
:   

    
`convert(input_path: pathlib.Path, output_dir: Union[str, pathlib.Path], *, file_type: str = 'json', n_sents: int = 1, seg_sents: bool = False, model: Optional[str] = None, morphology: bool = False, merge_subtokens: bool = False, converter: str = 'auto', ner_map: Optional[pathlib.Path] = None, lang: Optional[str] = None, concatenate: bool = False, silent: bool = True, msg: Optional[wasabi.printer.Printer] = None) ‑> None`
:   

    
`convert_cli(input_path: str = <typer.models.ArgumentInfo object>, output_dir: pathlib.Path = <typer.models.ArgumentInfo object>, file_type: spacy.cli.convert.FileTypes = <typer.models.OptionInfo object>, n_sents: int = <typer.models.OptionInfo object>, seg_sents: bool = <typer.models.OptionInfo object>, model: Optional[str] = <typer.models.OptionInfo object>, morphology: bool = <typer.models.OptionInfo object>, merge_subtokens: bool = <typer.models.OptionInfo object>, converter: str = <typer.models.OptionInfo object>, ner_map: Optional[pathlib.Path] = <typer.models.OptionInfo object>, lang: Optional[str] = <typer.models.OptionInfo object>, concatenate: bool = <typer.models.OptionInfo object>)`
:   Convert files into json or DocBin format for training. The resulting .spacy
    file can be used with the train command and other experiment management
    functions.
    
    If no output_dir is specified and the output format is JSON, the data
    is written to stdout, so you can pipe them forward to a JSON file:
    $ spacy convert some_file.conllu --file-type json > some_file.json
    
    DOCS: https://spacy.io/api/cli#convert

    
`verify_cli_args(msg: wasabi.printer.Printer, input_path: pathlib.Path, output_dir: Union[str, pathlib.Path], file_type: str, converter: str, ner_map: Optional[pathlib.Path])`
:   

    
`walk_directory(path: pathlib.Path, converter: str) ‑> List[pathlib.Path]`
:   

Classes
-------

`FileTypes(value, names=None, *, module=None, qualname=None, type=None, start=1)`
:   An enumeration.

    ### Ancestors (in MRO)

    * builtins.str
    * enum.Enum

    ### Class variables

    `json`
    :

    `spacy`
    :