Module spacy.cli.pretrain
=========================

Functions
---------

    
`pretrain_cli(ctx: typer.models.Context, config_path: pathlib.Path = <typer.models.ArgumentInfo object>, output_dir: pathlib.Path = <typer.models.ArgumentInfo object>, code_path: Optional[pathlib.Path] = <typer.models.OptionInfo object>, resume_path: Optional[pathlib.Path] = <typer.models.OptionInfo object>, epoch_resume: Optional[int] = <typer.models.OptionInfo object>, use_gpu: int = <typer.models.OptionInfo object>)`
:   Pre-train the 'token-to-vector' (tok2vec) layer of pipeline components,
    using an approximate language-modelling objective. Two objective types
    are available, vector-based and character-based.
    
    In the vector-based objective, we load word vectors that have been trained
    using a word2vec-style distributional similarity algorithm, and train a
    component like a CNN, BiLSTM, etc to predict vectors which match the
    pretrained ones. The weights are saved to a directory after each epoch. You
    can then pass a path to one of these pretrained weights files to the
    'spacy train' command.
    
    This technique may be especially helpful if you have little labelled data.
    However, it's still quite experimental, so your mileage may vary.
    
    To load the weights back in during 'spacy train', you need to ensure
    all settings are the same between pretraining and training. Ideally,
    this is done by using the same config file for both commands.
    
    DOCS: https://spacy.io/api/cli#pretrain

    
`verify_cli_args(config_path, output_dir, resume_path, epoch_resume)`
: