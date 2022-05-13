Module spacy.lexeme
===================

Classes
-------

`Lexeme(...)`
:   Lexeme(Vocab vocab, attr_t orth)
    An entry in the vocabulary. A `Lexeme` has no string context – it's a
        word-type, as opposed to a word token.  It therefore has no part-of-speech
        tag, dependency parse, or lemma (lemmatization depends on the
        part-of-speech tag).
    
        DOCS: https://spacy.io/api/lexeme
        
    
    Create a Lexeme object.
    
    vocab (Vocab): The parent vocabulary
    orth (uint64): The orth id of the lexeme.
    Returns (Lexeme): The newly constructd object.

    ### Instance variables

    `cluster`
    :   RETURNS (int): Brown cluster ID.

    `flags`
    :   RETURNS (uint64): Container of the lexeme's binary flags.

    `has_vector`
    :   RETURNS (bool): Whether a word vector is associated with the object.

    `is_alpha`
    :   RETURNS (bool): Whether the lexeme consists of alphabetic
        characters. Equivalent to `lexeme.text.isalpha()`.

    `is_ascii`
    :   RETURNS (bool): Whether the lexeme consists of ASCII characters.
        Equivalent to `[any(ord(c) >= 128 for c in lexeme.text)]`.

    `is_bracket`
    :   RETURNS (bool): Whether the lexeme is a bracket.

    `is_currency`
    :   RETURNS (bool): Whether the lexeme is a currency symbol, e.g. $, €.

    `is_digit`
    :   RETURNS (bool): Whether the lexeme consists of digits. Equivalent
        to `lexeme.text.isdigit()`.

    `is_left_punct`
    :   RETURNS (bool): Whether the lexeme is left punctuation, e.g. (.

    `is_lower`
    :   RETURNS (bool): Whether the lexeme is in lowercase. Equivalent to
        `lexeme.text.islower()`.

    `is_oov`
    :   RETURNS (bool): Whether the lexeme is out-of-vocabulary.

    `is_punct`
    :   RETURNS (bool): Whether the lexeme is punctuation.

    `is_quote`
    :   RETURNS (bool): Whether the lexeme is a quotation mark.

    `is_right_punct`
    :   RETURNS (bool): Whether the lexeme is right punctuation, e.g. ).

    `is_space`
    :   RETURNS (bool): Whether the lexeme consist of whitespace characters.
        Equivalent to `lexeme.text.isspace()`.

    `is_stop`
    :   RETURNS (bool): Whether the lexeme is a stop word.

    `is_title`
    :   RETURNS (bool): Whether the lexeme is in titlecase. Equivalent to
        `lexeme.text.istitle()`.

    `is_upper`
    :   RETURNS (bool): Whether the lexeme is in uppercase. Equivalent to
        `lexeme.text.isupper()`.

    `lang`
    :   RETURNS (uint64): Language of the parent vocabulary.

    `lang_`
    :   RETURNS (str): Language of the parent vocabulary.

    `like_email`
    :   RETURNS (bool): Whether the lexeme resembles an email address.

    `like_num`
    :   RETURNS (bool): Whether the lexeme represents a number, e.g. "10.9",
        "10", "ten", etc.

    `like_url`
    :   RETURNS (bool): Whether the lexeme resembles a URL.

    `lower`
    :   RETURNS (str): Lowercase form of the lexeme.

    `lower_`
    :   RETURNS (str): Lowercase form of the word.

    `norm`
    :   RETURNS (uint64): The lexeme's norm, i.e. a normalised form of the
        lexeme text.

    `norm_`
    :   RETURNS (str): The lexeme's norm, i.e. a normalised form of the
        lexeme text.

    `orth`
    :   Return an attribute of instance, which is of type owner.

    `orth_`
    :   RETURNS (str): The original verbatim text of the lexeme
        (identical to `Lexeme.text`). Exists mostly for consistency with
        the other attributes.

    `prefix`
    :   RETURNS (uint64): Length-N substring from the start of the word.
        Defaults to `N=1`.

    `prefix_`
    :   RETURNS (str): Length-N substring from the start of the word.
        Defaults to `N=1`.

    `prob`
    :   RETURNS (float): Smoothed log probability estimate of the lexeme's
        type.

    `rank`
    :   RETURNS (str): Sequential ID of the lexeme's lexical type, used
        to index into tables, e.g. for word vectors.

    `sentiment`
    :   RETURNS (float): A scalar value indicating the positivity or
        negativity of the lexeme.

    `shape`
    :   RETURNS (uint64): Transform of the word's string, to show
        orthographic features.

    `shape_`
    :   RETURNS (str): Transform of the word's string, to show
        orthographic features.

    `suffix`
    :   RETURNS (uint64): Length-N substring from the end of the word.
        Defaults to `N=3`.

    `suffix_`
    :   RETURNS (str): Length-N substring from the end of the word.
        Defaults to `N=3`.

    `text`
    :   RETURNS (str): The original verbatim text of the lexeme.

    `vector`
    :   A real-valued meaning representation.
        
        RETURNS (numpy.ndarray[ndim=1, dtype='float32']): A 1D numpy array
            representing the lexeme's semantics.

    `vector_norm`
    :   RETURNS (float): The L2 norm of the vector representation.

    `vocab`
    :   Return an attribute of instance, which is of type owner.

    ### Methods

    `check_flag(...)`
    :   Lexeme.check_flag(self, attr_id_t flag_id)
        Check the value of a boolean flag.
        
                flag_id (int): The attribute ID of the flag to query.
                RETURNS (bool): The value of the flag.

    `set_attrs(...)`
    :   Lexeme.set_attrs(self, **attrs)

    `set_flag(...)`
    :   Lexeme.set_flag(self, attr_id_t flag_id, bool value)
        Change the value of a boolean flag.
        
                flag_id (int): The attribute ID of the flag to set.
                value (bool): The new value of the flag.

    `similarity(...)`
    :   Lexeme.similarity(self, other)
        Compute a semantic similarity estimate. Defaults to cosine over
                vectors.
        
                other (object): The object to compare with. By default, accepts `Doc`,
                    `Span`, `Token` and `Lexeme` objects.
                RETURNS (float): A scalar similarity score. Higher is more similar.