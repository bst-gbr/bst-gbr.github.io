Module spacy.ml.extract_spans
=============================

Functions
---------

    
`extract_spans() ‑> thinc.model.Model[typing.Tuple[thinc.types.Ragged, thinc.types.Ragged], thinc.types.Ragged]`
:   Extract spans from a sequence of source arrays, as specified by an array
    of (start, end) indices. The output is a ragged array of the
    extracted spans.

    
`forward(model: thinc.model.Model, source_spans: Tuple[thinc.types.Ragged, thinc.types.Ragged], is_train: bool) ‑> Tuple[thinc.types.Ragged, Callable]`
:   Get subsequences from source vectors.

    
`init(model, X=None, Y=None)`
: