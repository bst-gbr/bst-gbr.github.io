Module spacy.lang.es.lemmatizer
===============================

Classes
-------

`SpanishLemmatizer(vocab: spacy.vocab.Vocab, model: Optional[thinc.model.Model], name: str = 'lemmatizer', *, mode: str = 'lookup', overwrite: bool = False, scorer: Optional[Callable] = <function lemmatizer_score>)`
:   Spanish rule-based lemmatizer with morph-based rule selection.
    
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

    `lemmatize_adj(self, word: str, features: List[str], rule: str, index: List[str]) ‑> List[str]`
    :   Lemmatize an adjective.
        
        word (str): The word to lemmatize.
        features (List[str]): The morphological features as a list of Feat=Val
            pairs.
        index (List[str]): The POS-specific lookup list.
        
        RETURNS (List[str]): The list of lemmas.

    `lemmatize_adv(self, word: str, features: List[str], rule: str, index: List[str]) ‑> List[str]`
    :   Lemmatize an adverb.
        
        word (str): The word to lemmatize.
        features (List[str]): The morphological features as a list of Feat=Val
            pairs.
        index (List[str]): The POS-specific lookup list.
        
        RETURNS (List[str]): The list of lemmas.

    `lemmatize_det(self, word: str, features: List[str], rule: str, index: List[str]) ‑> List[str]`
    :   Lemmatize a determiner.
        
        word (str): The word to lemmatize.
        features (List[str]): The morphological features as a list of Feat=Val
            pairs.
        index (List[str]): The POS-specific lookup list.
        
        RETURNS (List[str]): The list of lemmas.

    `lemmatize_noun(self, word: str, features: List[str], rule: str, index: List[str]) ‑> List[str]`
    :   Lemmatize a noun.
        
        word (str): The word to lemmatize.
        features (List[str]): The morphological features as a list of Feat=Val
            pairs.
        index (List[str]): The POS-specific lookup list.
        
        RETURNS (List[str]): The list of lemmas.

    `lemmatize_num(self, word: str, features: List[str], rule: str, index: List[str]) ‑> List[str]`
    :   Lemmatize a numeral.
        
        word (str): The word to lemmatize.
        features (List[str]): The morphological features as a list of Feat=Val
            pairs.
        index (List[str]): The POS-specific lookup list.
        
        RETURNS (List[str]): The list of lemmas.

    `lemmatize_pron(self, word: str, features: List[str], rule: Optional[str], index: List[str]) ‑> List[str]`
    :   Lemmatize a pronoun.
        
        word (str): The word to lemmatize.
        features (List[str]): The morphological features as a list of Feat=Val
            pairs.
        index (List[str]): The POS-specific lookup list.
        
        RETURNS (List[str]): The list of lemmas.

    `lemmatize_verb(self, word: str, features: List[str], rule: Optional[str], index: List[str]) ‑> List[str]`
    :   Lemmatize a verb.
        
        word (str): The word to lemmatize.
        features (List[str]): The morphological features as a list of Feat=Val
            pairs.
        index (List[str]): The POS-specific lookup list.
        
        RETURNS (List[str]): The list of lemmas.

    `lemmatize_verb_pron(self, word: str, features: List[str], rule: Optional[str], index: List[str]) ‑> List[str]`
    :

    `select_rule(self, pos: str, features: List[str]) ‑> Optional[str]`
    :