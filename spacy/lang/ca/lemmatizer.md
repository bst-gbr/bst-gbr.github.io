Module spacy.lang.ca.lemmatizer
===============================

Classes
-------

`CatalanLemmatizer(vocab: spacy.vocab.Vocab, model: Optional[thinc.model.Model], name: str = 'lemmatizer', *, mode: str = 'lookup', overwrite: bool = False, scorer: Optional[Callable] = <function lemmatizer_score>)`
:   Copied from French Lemmatizer
    Catalan language lemmatizer applies the default rule based lemmatization
    procedure with some modifications for better Catalan language support.
    
    The parts of speech 'ADV', 'PRON', 'DET', 'ADP' and 'AUX' are added to use
    the rule-based lemmatization. As a last resort, the lemmatizer checks in
    the lookup table.
    
    Initialize a Lemmatizer.
    
    vocab (Vocab): The vocab.
    model (Model): A model (not yet implemented).
    name (str): The component name. Defaults to "lemmatizer".
    mode (str): The lemmatizer mode: "lookup", "rule". Defaults to "lookup".
    overwrite (bool): Whether to overwrite existing lemmas. Defaults to
        `False`.
    scorer (Optional[Callable]): The scoring method. Defaults to
        Scorer.score_token_attr for the attribute "lemma".
    
    DOCS: https://spacy.io/api/lemmatizer#init

    ### Ancestors (in MRO)

    * spacy.pipeline.lemmatizer.Lemmatizer
    * spacy.pipeline.pipe.Pipe