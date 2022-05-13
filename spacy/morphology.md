Module spacy.morphology
=======================

Functions
---------

    
`unpickle_morphology(strings, tags)`
:   

Classes
-------

`Morphology(*args, **kwargs)`
:   Morphology(StringStore strings)
    Store the possible morphological analyses for a language, and index them
        by hash.
    
        To save space on each token, tokens only know the hash of their
        morphological analysis, so queries of morphological attributes are delegated
        to this class.

    ### Class variables

    `EMPTY_MORPH`
    :

    `FEATURE_SEP`
    :

    `FIELD_SEP`
    :

    `VALUE_SEP`
    :

    ### Static methods

    `dict_to_feats(...)`
    :   Morphology.dict_to_feats(feats_dict)

    `feats_to_dict(...)`
    :   Morphology.feats_to_dict(feats)

    ### Instance variables

    `mem`
    :   Return an attribute of instance, which is of type owner.

    `strings`
    :   Return an attribute of instance, which is of type owner.

    ### Methods

    `add(...)`
    :   Morphology.add(self, features)
        Insert a morphological analysis in the morphology table, if not
                already present. The morphological analysis may be provided in the UD
                FEATS format as a string or in the tag map dict format.
                Returns the hash of the new analysis.

    `get(...)`
    :   Morphology.get(self, hash_t morph)

    `normalize_attrs(...)`
    :   Morphology.normalize_attrs(self, attrs)
        Convert attrs dict so that POS is always by ID, other features are
                by string. Values separated by VALUE_SEP are sorted.

    `normalize_features(...)`
    :   Morphology.normalize_features(self, features)
        Create a normalized FEATS string from a features string or dict.
        
                features (Union[dict, str]): Features as dict or UFEATS string.
                RETURNS (str): Features as normalized UFEATS string.