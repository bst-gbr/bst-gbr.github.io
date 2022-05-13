Module spacy.cli.evaluate
=========================

Functions
---------

    
`evaluate(model: str, data_path: pathlib.Path, output: Optional[pathlib.Path] = None, use_gpu: int = -1, gold_preproc: bool = False, displacy_path: Optional[pathlib.Path] = None, displacy_limit: int = 25, silent: bool = True, spans_key: str = 'sc') ‑> Dict[str, Any]`
:   

    
`evaluate_cli(model: str = <typer.models.ArgumentInfo object>, data_path: pathlib.Path = <typer.models.ArgumentInfo object>, output: Optional[pathlib.Path] = <typer.models.OptionInfo object>, code_path: Optional[pathlib.Path] = <typer.models.OptionInfo object>, use_gpu: int = <typer.models.OptionInfo object>, gold_preproc: bool = <typer.models.OptionInfo object>, displacy_path: Optional[pathlib.Path] = <typer.models.OptionInfo object>, displacy_limit: int = <typer.models.OptionInfo object>)`
:   Evaluate a trained pipeline. Expects a loadable spaCy pipeline and evaluation
    data in the binary .spacy format. The --gold-preproc option sets up the
    evaluation examples with gold-standard sentences and tokens for the
    predictions. Gold preprocessing helps the annotations align to the
    tokenization, and may result in sequences of more consistent length. However,
    it may reduce runtime accuracy due to train/test skew. To render a sample of
    dependency parses in a HTML file, set as output directory as the
    displacy_path argument.
    
    DOCS: https://spacy.io/api/cli#evaluate

    
`handle_scores_per_type(scores: Dict[str, Any], data: Dict[str, Any] = {}, *, spans_key: str = 'sc', silent: bool = False) ‑> Dict[str, Any]`
:   

    
`print_prf_per_type(msg: wasabi.printer.Printer, scores: Dict[str, Dict[str, float]], name: str, type: str) ‑> None`
:   

    
`print_textcats_auc_per_cat(msg: wasabi.printer.Printer, scores: Dict[str, Dict[str, float]]) ‑> None`
:   

    
`render_parses(docs: List[spacy.tokens.doc.Doc], output_path: pathlib.Path, model_name: str = '', limit: int = 250, deps: bool = True, ents: bool = True)`
: