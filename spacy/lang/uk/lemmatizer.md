Module spacy.lang.uk.lemmatizer
===============================

Classes
-------

`UkrainianLemmatizer(vocab: spacy.vocab.Vocab, model: Optional[thinc.model.Model], name: str = 'lemmatizer', *, mode: str = 'pymorphy2', overwrite: bool = False, scorer: Optional[Callable] = <function lemmatizer_score>)`
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

    * spacy.lang.ru.lemmatizer.RussianLemmatizer
    * spacy.pipeline.lemmatizer.Lemmatizer
    * spacy.pipeline.pipe.Pipe