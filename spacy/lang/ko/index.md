Module spacy.lang.ko
====================

Sub-modules
-----------
* spacy.lang.ko.examples
* spacy.lang.ko.lex_attrs
* spacy.lang.ko.stop_words
* spacy.lang.ko.tag_map

Classes
-------

`Korean(vocab: Union[spacy.vocab.Vocab, bool] = True, *, max_length: int = 1000000, meta: Dict[str, Any] = {}, create_tokenizer: Optional[Callable[[ForwardRef('Language')], Callable[[str], spacy.tokens.doc.Doc]]] = None, batch_size: int = 1000, **kwargs)`
:   A text-processing pipeline. Usually you'll load this once per process,
    and pass the instance around your application.
    
    Defaults (class): Settings, data and factory methods for creating the `nlp`
        object and processing pipeline.
    lang (str): IETF language code, such as 'en'.
    
    DOCS: https://spacy.io/api/language
    
    Initialise a Language object.
    
    vocab (Vocab): A `Vocab` object. If `True`, a vocab is created.
    meta (dict): Custom meta data for the Language class. Is written to by
        models to add model meta data.
    max_length (int): Maximum number of characters in a single text. The
        current models may run out memory on extremely long texts, due to
        large internal allocations. You should segment these texts into
        meaningful units, e.g. paragraphs, subsections etc, before passing
        them to spaCy. Default maximum length is 1,000,000 charas (1mb). As
        a rule of thumb, if all pipeline components are enabled, spaCy's
        default models currently requires roughly 1GB of temporary memory per
        100,000 characters in one text.
    create_tokenizer (Callable): Function that takes the nlp object and
        returns a tokenizer.
    batch_size (int): Default batch size for pipe and evaluate.
    
    DOCS: https://spacy.io/api/language#init

    ### Ancestors (in MRO)

    * spacy.language.Language

    ### Class variables

    `default_config`
    :

    `lang: Optional[str]`
    :