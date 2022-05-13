Module spacy.lang.nl.syntax_iterators
=====================================

Functions
---------

    
`noun_chunks(doclike: Union[spacy.tokens.doc.Doc, spacy.tokens.span.Span]) ‑> Iterator[Tuple[int, int, int]]`
:   Detect base noun phrases from a dependency parse. Works on Doc and Span.
    The definition is inspired by https://www.nltk.org/book/ch07.html
    Consider : [Noun + determinant / adjective] and also [Pronoun]