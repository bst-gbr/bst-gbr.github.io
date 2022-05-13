Module spacy.lang.it.lemmatizer
===============================

Classes
-------

`ItalianLemmatizer(vocab: spacy.vocab.Vocab, model: Optional[thinc.model.Model], name: str = 'lemmatizer', *, mode: str = 'lookup', overwrite: bool = False, scorer: Optional[Callable] = <function lemmatizer_score>)`
:   This lemmatizer was adapted from the Polish one (version of April 2021).
    It implements lookup lemmatization based on the morphological lexicon
    morph-it (Baroni and Zanchetta). The table lemma_lookup with non-POS-aware
    entries is used as a backup for words that aren't handled by morph-it.
    
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

    ### Methods

    `lemmatize_adj(self, string: str, morphology: dict, lookup_table: Dict[str, str]) ‑> List[str]`
    :

    `lemmatize_adp(self, string: str, morphology: dict, lookup_table: Dict[str, str]) ‑> List[str]`
    :

    `lemmatize_det(self, string: str, morphology: dict, lookup_table: Dict[str, str]) ‑> List[str]`
    :

    `lemmatize_noun(self, string: str, morphology: dict, lookup_table: Dict[str, str]) ‑> List[str]`
    :

    `lemmatize_pron(self, string: str, morphology: dict, lookup_table: Dict[str, str]) ‑> List[str]`
    :

    `pos_lookup_lemmatize(self, token: spacy.tokens.token.Token) ‑> List[str]`
    :