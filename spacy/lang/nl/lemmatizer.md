Module spacy.lang.nl.lemmatizer
===============================

Classes
-------

`DutchLemmatizer(vocab: spacy.vocab.Vocab, model: Optional[thinc.model.Model], name: str = 'lemmatizer', *, mode: str = 'lookup', overwrite: bool = False, scorer: Optional[Callable] = <function lemmatizer_score>)`
:   The Lemmatizer supports simple part-of-speech-sensitive suffix rules and
    lookup tables.
    
    DOCS: https://spacy.io/api/lemmatizer
    
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

    `lookup_lemmatize(self, token: spacy.tokens.token.Token) ‑> List[str]`
    :   Overrides parent method so that a lowercased version of the string
        is used to search the lookup table. This is necessary because our
        lookup table consists entirely of lowercase keys.