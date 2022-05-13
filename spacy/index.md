Module spacy
============

Sub-modules
-----------
* spacy.about
* spacy.attrs
* spacy.cli
* spacy.compat
* spacy.displacy
* spacy.errors
* spacy.git_info
* spacy.glossary
* spacy.kb
* spacy.lang
* spacy.language
* spacy.lexeme
* spacy.lookups
* spacy.matcher
* spacy.ml
* spacy.morphology
* spacy.parts_of_speech
* spacy.pipe_analysis
* spacy.pipeline
* spacy.schemas
* spacy.scorer
* spacy.strings
* spacy.symbols
* spacy.tests
* spacy.tokenizer
* spacy.tokens
* spacy.training
* spacy.ty
* spacy.util
* spacy.vectors
* spacy.vocab

Functions
---------

    
`blank(name: str, *, vocab: Union[spacy.vocab.Vocab, bool] = True, config: Union[Dict[str, Any], thinc.config.Config] = {}, meta: Dict[str, Any] = {}) ‑> spacy.language.Language`
:   Create a blank nlp object for a given language code.
    
    name (str): The language code, e.g. "en".
    vocab (Vocab): A Vocab object. If True, a vocab is created.
    config (Dict[str, Any] / Config): Optional config overrides.
    meta (Dict[str, Any]): Overrides for nlp.meta.
    RETURNS (Language): The nlp object.

    
`load(name: Union[str, pathlib.Path], *, vocab: Union[spacy.vocab.Vocab, bool] = True, disable: Iterable[str] = [], exclude: Iterable[str] = [], config: Union[Dict[str, Any], thinc.config.Config] = {}) ‑> spacy.language.Language`
:   Load a spaCy model from an installed package or a local path.
    
    name (str): Package name or model path.
    vocab (Vocab): A Vocab object. If True, a vocab is created.
    disable (Iterable[str]): Names of pipeline components to disable. Disabled
        pipes will be loaded but they won't be run unless you explicitly
        enable them by calling nlp.enable_pipe.
    exclude (Iterable[str]): Names of pipeline components to exclude. Excluded
        components won't be loaded.
    config (Dict[str, Any] / Config): Config overrides as nested dict or dict
        keyed by section values in dot notation.
    RETURNS (Language): The loaded nlp object.