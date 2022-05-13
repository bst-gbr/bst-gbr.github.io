Module spacy.ml.models.parser
=============================

Functions
---------

    
`build_tb_parser_model(tok2vec: thinc.model.Model[typing.List[spacy.tokens.doc.Doc], typing.List[thinc.types.Floats2d]], state_type: typing_extensions.Literal['parser', 'ner'], extra_state_tokens: bool, hidden_width: int, maxout_pieces: int, use_upper: bool, nO: Optional[int] = None) ‑> thinc.model.Model`
:   Build a transition-based parser model. Can apply to NER or dependency-parsing.
    
    Transition-based parsing is an approach to structured prediction where the
    task of predicting the structure is mapped to a series of state transitions.
    You might find this tutorial helpful as background:
    https://explosion.ai/blog/parsing-english-in-python
    
    The neural network state prediction model consists of either two or three
    subnetworks:
    
    * tok2vec: Map each token into a vector representations. This subnetwork
        is run once for each batch.
    * lower: Construct a feature-specific vector for each (token, feature) pair.
        This is also run once for each batch. Constructing the state
        representation is then simply a matter of summing the component features
        and applying the non-linearity.
    * upper (optional): A feed-forward network that predicts scores from the
        state representation. If not present, the output from the lower model is
        used as action scores directly.
    
    tok2vec (Model[List[Doc], List[Floats2d]]):
        Subnetwork to map tokens into vector representations.
    state_type (str):
        String value denoting the type of parser model: "parser" or "ner"
    extra_state_tokens (bool): Whether or not to use additional tokens in the context
        to construct the state vector. Defaults to `False`, which means 3 and 8
        for the NER and parser respectively. When set to `True`, this would become 6
        feature sets (for the NER) or 13 (for the parser).
    hidden_width (int): The width of the hidden layer.
    maxout_pieces (int): How many pieces to use in the state prediction layer.
        Recommended values are 1, 2 or 3. If 1, the maxout non-linearity
        is replaced with a ReLu non-linearity if use_upper=True, and no
        non-linearity if use_upper=False.
    use_upper (bool): Whether to use an additional hidden layer after the state
        vector in order to predict the action scores. It is recommended to set
        this to False for large pretrained models such as transformers, and True
        for smaller networks. The upper layer is computed on CPU, which becomes
        a bottleneck on larger GPU-based models, where it's also less necessary.
    nO (int or None): The number of actions the model will predict between.
        Usually inferred from data at the beginning of training, or loaded from
        disk.

    
`resize_output(model, new_nO)`
: