Module spacy.lang.el.lemmatizer
===============================

Classes
-------

`GreekLemmatizer(vocab: spacy.vocab.Vocab, model: Optional[thinc.model.Model], name: str = 'lemmatizer', *, mode: str = 'lookup', overwrite: bool = False, scorer: Optional[Callable] = <function lemmatizer_score>)`
:   Greek language lemmatizer applies the default rule based lemmatization
    procedure with some modifications for better Greek language support.
    
    The first modification is that it checks if the word for lemmatization is
    already a lemma and if yes, it just returns it.
    The second modification is about removing the base forms function which is
    not applicable for Greek language.
    
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

    `rule_lemmatize(self, token: spacy.tokens.token.Token) ‑> List[str]`
    :   Lemmatize using a rule-based approach.
        
        token (Token): The token to lemmatize.
        RETURNS (list): The available lemmas for the string.