Module spacy.ml.models.tagger
=============================

Functions
---------

    
`build_tagger_model(tok2vec: thinc.model.Model[typing.List[spacy.tokens.doc.Doc], typing.List[thinc.types.Floats2d]], nO: Optional[int] = None) ‑> thinc.model.Model[typing.List[spacy.tokens.doc.Doc], typing.List[thinc.types.Floats2d]]`
:   Build a tagger model, using a provided token-to-vector component. The tagger
    model simply adds a linear layer with softmax activation to predict scores
    given the token vectors.
    
    tok2vec (Model[List[Doc], List[Floats2d]]): The token-to-vector subnetwork.
    nO (int or None): The number of tags to output. Inferred from the data if None.