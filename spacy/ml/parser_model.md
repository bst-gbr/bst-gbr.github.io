Module spacy.ml.parser_model
============================

Functions
---------

    
`step_forward(model: spacy.ml.parser_model.ParserStepModel, states, is_train)`
:   

Classes
-------

`ParserStepModel(docs, layers, *, has_upper, unseen_classes=None, train=True, dropout=0.1)`
:   Class for implementing Thinc models and layers.
    
    ParserStepModel.__init__(self, docs, layers, *, has_upper, unseen_classes=None, train=True, dropout=0.1)

    ### Ancestors (in MRO)

    * thinc.model.Model
    * typing.Generic

    ### Class variables

    `global_id: int`
    :

    `global_id_lock: <built-in function allocate_lock>`
    :

    ### Instance variables

    `id: int`
    :   Return an attribute of instance, which is of type owner.

    `init: Callable`
    :   Return an attribute of instance, which is of type owner.

    `nO`
    :   ParserStepModel.nO(self)

    `name: str`
    :   Return an attribute of instance, which is of type owner.

    `ops: thinc.backends.ops.Ops`
    :   Return an attribute of instance, which is of type owner.

    ### Methods

    `backprop_step(self, token_ids, d_vector, get_d_tokvecs)`
    :   ParserStepModel.backprop_step(self, token_ids, d_vector, get_d_tokvecs)

    `class_is_unseen(self, class_)`
    :   ParserStepModel.class_is_unseen(self, class_)

    `clear_memory(self)`
    :   ParserStepModel.clear_memory(self)

    `finish_steps(self, golds)`
    :   ParserStepModel.finish_steps(self, golds)

    `get_token_ids(self, states)`
    :   ParserStepModel.get_token_ids(self, states)

    `mark_class_seen(self, class_)`
    :   ParserStepModel.mark_class_seen(self, class_)

    `mark_class_unseen(self, class_)`
    :   ParserStepModel.mark_class_unseen(self, class_)

`precompute_hiddens(*args, **kwargs)`
:   precompute_hiddens(batch_size, tokvecs, lower_model, cuda_stream=None, activation='maxout', train=False)
    Allow a model to be "primed" by pre-computing input features in bulk.
    
        This is used for the parser, where we want to take a batch of documents,
        and compute vectors for each (token, position) pair. These vectors can then
        be reused, especially for beam-search.
    
        Let's say we're using 12 features for each state, e.g. word at start of
        buffer, three words on stack, their children, etc. In the normal arc-eager
        system, a document of length N is processed in 2*N states. This means we'll
        create 2*N*12 feature vectors --- but if we pre-compute, we only need
        N*12 vector computations. The saving for beam-search is much better:
        if we have a beam of k, we'll normally make 2*N*12*K computations --
        so we can save the factor k. This also gives a nice CPU/GPU division:
        we can do all our hard maths up front, packed into large multiplications,
        and do the hard-to-program parsing on the CPU.

    ### Instance variables

    `nF`
    :   Return an attribute of instance, which is of type owner.

    `nO`
    :   Return an attribute of instance, which is of type owner.

    `nP`
    :   Return an attribute of instance, which is of type owner.

    `numpy_ops`
    :   numpy_ops: object

    `ops`
    :   ops: object

    ### Methods

    `begin_update(...)`
    :   precompute_hiddens.begin_update(self, token_ids)

    `get_dim(...)`
    :   precompute_hiddens.get_dim(self, name)

    `has_dim(...)`
    :   precompute_hiddens.has_dim(self, name)

    `predict(...)`
    :   precompute_hiddens.predict(self, X)

    `set_dim(...)`
    :   precompute_hiddens.set_dim(self, name, value)