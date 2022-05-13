Module spacy.ml.models.textcat
==============================

Functions
---------

    
`build_bow_text_classifier(exclusive_classes: bool, ngram_size: int, no_output_layer: bool, nO: Optional[int] = None) ‑> thinc.model.Model[typing.List[spacy.tokens.doc.Doc], thinc.types.Floats2d]`
:   

    
`build_simple_cnn_text_classifier(tok2vec: thinc.model.Model, exclusive_classes: bool, nO: Optional[int] = None) ‑> thinc.model.Model[typing.List[spacy.tokens.doc.Doc], thinc.types.Floats2d]`
:   Build a simple CNN text classifier, given a token-to-vector model as inputs.
    If exclusive_classes=True, a softmax non-linearity is applied, so that the
    outputs sum to 1. If exclusive_classes=False, a logistic non-linearity
    is applied instead, so that outputs are in the range [0, 1].

    
`build_text_classifier_lowdata(width: int, dropout: Optional[float], nO: Optional[int] = None) ‑> thinc.model.Model[typing.List[spacy.tokens.doc.Doc], thinc.types.Floats2d]`
:   

    
`build_text_classifier_v2(tok2vec: thinc.model.Model[typing.List[spacy.tokens.doc.Doc], typing.List[thinc.types.Floats2d]], linear_model: thinc.model.Model[typing.List[spacy.tokens.doc.Doc], thinc.types.Floats2d], nO: Optional[int] = None) ‑> thinc.model.Model[typing.List[spacy.tokens.doc.Doc], thinc.types.Floats2d]`
:   

    
`init_ensemble_textcat(model, X, Y) ‑> thinc.model.Model`
:   

    
`resize_and_set_ref(model, new_nO, resizable_layer)`
: