Module spacy.ml.models.entity_linker
====================================

Functions
---------

    
`build_nel_encoder(tok2vec: thinc.model.Model, nO: Optional[int] = None) ‑> thinc.model.Model[typing.List[spacy.tokens.doc.Doc], thinc.types.Floats2d]`
:   

    
`create_candidates() ‑> Callable[[spacy.kb.KnowledgeBase, spacy.tokens.span.Span], Iterable[spacy.kb.Candidate]]`
:   

    
`empty_kb(entity_vector_length: int) ‑> Callable[[spacy.vocab.Vocab], spacy.kb.KnowledgeBase]`
:   

    
`load_kb(kb_path: pathlib.Path) ‑> Callable[[spacy.vocab.Vocab], spacy.kb.KnowledgeBase]`
: