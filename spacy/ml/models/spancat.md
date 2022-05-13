Module spacy.ml.models.spancat
==============================

Functions
---------

    
`build_linear_logistic(nO=None, nI=None) ‑> thinc.model.Model[thinc.types.Floats2d, thinc.types.Floats2d]`
:   An output layer for multi-label classification. It uses a linear layer
    followed by a logistic activation.

    
`build_mean_max_reducer(hidden_size: int) ‑> thinc.model.Model[thinc.types.Ragged, thinc.types.Floats2d]`
:   Reduce sequences by concatenating their mean and max pooled vectors,
    and then combine the concatenated vectors with a hidden layer.

    
`build_spancat_model(tok2vec: thinc.model.Model[typing.List[spacy.tokens.doc.Doc], typing.List[thinc.types.Floats2d]], reducer: thinc.model.Model[thinc.types.Ragged, thinc.types.Floats2d], scorer: thinc.model.Model[thinc.types.Floats2d, thinc.types.Floats2d]) ‑> thinc.model.Model[typing.Tuple[typing.List[spacy.tokens.doc.Doc], thinc.types.Ragged], thinc.types.Floats2d]`
:   Build a span categorizer model, given a token-to-vector model, a
    reducer model to map the sequence of vectors for each span down to a single
    vector, and a scorer model to map the vectors to probabilities.
    
    tok2vec (Model[List[Doc], List[Floats2d]]): The tok2vec model.
    reducer (Model[Ragged, Floats2d]): The reducer model.
    scorer (Model[Floats2d, Floats2d]): The scorer model.