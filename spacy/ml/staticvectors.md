Module spacy.ml.staticvectors
=============================

Functions
---------

    
`StaticVectors(nO: Optional[int] = None, nM: Optional[int] = None, *, dropout: Optional[float] = None, init_W: Callable = <function glorot_uniform_init>, key_attr: str = 'ORTH') ‑> thinc.model.Model[typing.List[spacy.tokens.doc.Doc], thinc.types.Ragged]`
:   Embed Doc objects with their vocab's vectors table, applying a learned
    linear projection to control the dimensionality. If a dropout rate is
    specified, the dropout is applied per dimension over the whole batch.

    
`forward(model: thinc.model.Model[typing.List[spacy.tokens.doc.Doc], thinc.types.Ragged], docs: List[spacy.tokens.doc.Doc], is_train: bool) ‑> Tuple[thinc.types.Ragged, Callable]`
:   

    
`init(init_W: Callable, model: thinc.model.Model[typing.List[spacy.tokens.doc.Doc], thinc.types.Ragged], X: Optional[List[spacy.tokens.doc.Doc]] = None, Y: Optional[thinc.types.Ragged] = None) ‑> thinc.model.Model[typing.List[spacy.tokens.doc.Doc], thinc.types.Ragged]`
: