Module spacy.ml.models.multi_task
=================================

Functions
---------

    
`build_cloze_characters_multi_task_model(vocab: Vocab, tok2vec: thinc.model.Model, maxout_pieces: int, hidden_size: int, nr_char: int) ‑> thinc.model.Model`
:   

    
`build_cloze_multi_task_model(vocab: Vocab, tok2vec: thinc.model.Model, maxout_pieces: int, hidden_size: int) ‑> thinc.model.Model`
:   

    
`build_masked_language_model(vocab: Vocab, wrapped_model: thinc.model.Model, mask_prob: float = 0.15) ‑> thinc.model.Model`
:   Convert a model into a BERT-style masked language model

    
`build_multi_task_model(tok2vec: thinc.model.Model, maxout_pieces: int, token_vector_width: int, nO: Optional[int] = None) ‑> thinc.model.Model`
:   

    
`create_pretrain_characters(maxout_pieces: int, hidden_size: int, n_characters: int) ‑> Callable[[Vocab, thinc.model.Model], thinc.model.Model]`
:   

    
`create_pretrain_vectors(maxout_pieces: int, hidden_size: int, loss: str) ‑> Callable[[Vocab, thinc.model.Model], thinc.model.Model]`
:   

    
`get_characters_loss(ops, docs, prediction, nr_char)`
:   Compute a loss based on a number of characters predicted from the docs.

    
`get_vectors_loss(ops, docs, prediction, distance)`
:   Compute a loss based on a distance between the documents' vectors and
    the prediction.