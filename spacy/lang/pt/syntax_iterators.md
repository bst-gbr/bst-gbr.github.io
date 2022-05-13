Module spacy.lang.pt.syntax_iterators
=====================================

Functions
---------

    
`noun_chunks(doclike: Union[spacy.tokens.doc.Doc, spacy.tokens.span.Span]) ‑> Iterator[Tuple[int, int, int]]`
:   Detect base noun phrases from a dependency parse. Works on both Doc and Span.