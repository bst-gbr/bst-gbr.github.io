Module spacy.language
=====================

Functions
---------

    
`URL_MATCH(string, pos=0, endpos=9223372036854775807)`
:   Matches zero or more characters at the beginning of the string.

    
`create_tokenizer() ‑> Callable[[spacy.language.Language], spacy.tokenizer.Tokenizer]`
:   Registered function to create a tokenizer. Returns a factory that takes
    the nlp object and returns a Tokenizer instance using the language detaults.

    
`load_lookups_data(lang, tables)`
:   

Classes
-------

`BaseDefaults()`
:   Language data defaults, available via Language.Defaults. Can be
    overwritten by language subclasses by defining their own subclasses of
    Language.Defaults.

    ### Descendants

    * spacy.lang.af.AfrikaansDefaults
    * spacy.lang.am.AmharicDefaults
    * spacy.lang.ar.ArabicDefaults
    * spacy.lang.az.AzerbaijaniDefaults
    * spacy.lang.bg.BulgarianDefaults
    * spacy.lang.bn.BengaliDefaults
    * spacy.lang.ca.CatalanDefaults
    * spacy.lang.cs.CzechDefaults
    * spacy.lang.da.DanishDefaults
    * spacy.lang.de.GermanDefaults
    * spacy.lang.el.GreekDefaults
    * spacy.lang.en.EnglishDefaults
    * spacy.lang.es.SpanishDefaults
    * spacy.lang.et.EstonianDefaults
    * spacy.lang.eu.BasqueDefaults
    * spacy.lang.fa.PersianDefaults
    * spacy.lang.fi.FinnishDefaults
    * spacy.lang.fr.FrenchDefaults
    * spacy.lang.ga.IrishDefaults
    * spacy.lang.grc.AncientGreekDefaults
    * spacy.lang.gu.GujaratiDefaults
    * spacy.lang.he.HebrewDefaults
    * spacy.lang.hi.HindiDefaults
    * spacy.lang.hr.CroatianDefaults
    * spacy.lang.hu.HungarianDefaults
    * spacy.lang.hy.ArmenianDefaults
    * spacy.lang.id.IndonesianDefaults
    * spacy.lang.is.IcelandicDefaults
    * spacy.lang.it.ItalianDefaults
    * spacy.lang.ja.JapaneseDefaults
    * spacy.lang.kn.KannadaDefaults
    * spacy.lang.ko.KoreanDefaults
    * spacy.lang.ky.KyrgyzDefaults
    * spacy.lang.lb.LuxembourgishDefaults
    * spacy.lang.lij.LigurianDefaults
    * spacy.lang.lt.LithuanianDefaults
    * spacy.lang.lv.LatvianDefaults
    * spacy.lang.mk.MacedonianDefaults
    * spacy.lang.ml.MalayalamDefaults
    * spacy.lang.mr.MarathiDefaults
    * spacy.lang.nb.NorwegianDefaults
    * spacy.lang.ne.NepaliDefaults
    * spacy.lang.nl.DutchDefaults
    * spacy.lang.pl.PolishDefaults
    * spacy.lang.pt.PortugueseDefaults
    * spacy.lang.ro.RomanianDefaults
    * spacy.lang.ru.RussianDefaults
    * spacy.lang.sa.SanskritDefaults
    * spacy.lang.si.SinhalaDefaults
    * spacy.lang.sk.SlovakDefaults
    * spacy.lang.sl.SlovenianDefaults
    * spacy.lang.sq.AlbanianDefaults
    * spacy.lang.sr.SerbianDefaults
    * spacy.lang.sv.SwedishDefaults
    * spacy.lang.ta.TamilDefaults
    * spacy.lang.te.TeluguDefaults
    * spacy.lang.th.ThaiDefaults
    * spacy.lang.ti.TigrinyaDefaults
    * spacy.lang.tl.TagalogDefaults
    * spacy.lang.tn.SetswanaDefaults
    * spacy.lang.tr.TurkishDefaults
    * spacy.lang.tt.TatarDefaults
    * spacy.lang.uk.UkrainianDefaults
    * spacy.lang.ur.UrduDefaults
    * spacy.lang.vi.VietnameseDefaults
    * spacy.lang.yo.YorubaDefaults
    * spacy.lang.zh.ChineseDefaults

    ### Class variables

    `config: thinc.config.Config`
    :

    `infixes: Optional[Sequence[Union[str, Pattern[~AnyStr]]]]`
    :

    `lex_attr_getters: Dict[int, Callable[[str], Any]]`
    :

    `prefixes: Optional[Sequence[Union[str, Pattern[~AnyStr]]]]`
    :

    `stop_words: Set[str]`
    :

    `suffixes: Optional[Sequence[Union[str, Pattern[~AnyStr]]]]`
    :

    `syntax_iterators: Dict[str, Callable]`
    :

    `token_match: Optional[Callable]`
    :

    `tokenizer_exceptions: Dict[str, List[dict]]`
    :

    `writing_system`
    :

    ### Methods

    `url_match(string, pos=0, endpos=9223372036854775807) ‑> Optional[Callable]`
    :   Matches zero or more characters at the beginning of the string.

`DisabledPipes(nlp: spacy.language.Language, names: List[str])`
:   Manager for temporary pipeline disabling.

    ### Ancestors (in MRO)

    * builtins.list

    ### Methods

    `restore(self) ‑> None`
    :   Restore the pipeline to its state when DisabledPipes was created.

`FactoryMeta(factory: str, default_config: Optional[Dict[str, Any]] = None, assigns: Iterable[str] = (), requires: Iterable[str] = (), retokenizes: bool = False, scores: Iterable[str] = (), default_score_weights: Optional[Dict[str, Optional[float]]] = None)`
:   Dataclass containing information about a component and its defaults
    provided by the @Language.component or @Language.factory decorator. It's
    created whenever a component is defined and stored on the Language class for
    each component instance and factory instance.

    ### Class variables

    `assigns: Iterable[str]`
    :

    `default_config: Optional[Dict[str, Any]]`
    :

    `default_score_weights: Optional[Dict[str, Optional[float]]]`
    :

    `factory: str`
    :

    `requires: Iterable[str]`
    :

    `retokenizes: bool`
    :

    `scores: Iterable[str]`
    :

`Language(vocab: Union[spacy.vocab.Vocab, bool] = True, *, max_length: int = 1000000, meta: Dict[str, Any] = {}, create_tokenizer: Optional[Callable[[ForwardRef('Language')], Callable[[str], spacy.tokens.doc.Doc]]] = None, batch_size: int = 1000, **kwargs)`
:   A text-processing pipeline. Usually you'll load this once per process,
    and pass the instance around your application.
    
    Defaults (class): Settings, data and factory methods for creating the `nlp`
        object and processing pipeline.
    lang (str): IETF language code, such as 'en'.
    
    DOCS: https://spacy.io/api/language
    
    Initialise a Language object.
    
    vocab (Vocab): A `Vocab` object. If `True`, a vocab is created.
    meta (dict): Custom meta data for the Language class. Is written to by
        models to add model meta data.
    max_length (int): Maximum number of characters in a single text. The
        current models may run out memory on extremely long texts, due to
        large internal allocations. You should segment these texts into
        meaningful units, e.g. paragraphs, subsections etc, before passing
        them to spaCy. Default maximum length is 1,000,000 charas (1mb). As
        a rule of thumb, if all pipeline components are enabled, spaCy's
        default models currently requires roughly 1GB of temporary memory per
        100,000 characters in one text.
    create_tokenizer (Callable): Function that takes the nlp object and
        returns a tokenizer.
    batch_size (int): Default batch size for pipe and evaluate.
    
    DOCS: https://spacy.io/api/language#init

    ### Descendants

    * spacy.lang.af.Afrikaans
    * spacy.lang.am.Amharic
    * spacy.lang.ar.Arabic
    * spacy.lang.az.Azerbaijani
    * spacy.lang.bg.Bulgarian
    * spacy.lang.bn.Bengali
    * spacy.lang.ca.Catalan
    * spacy.lang.cs.Czech
    * spacy.lang.da.Danish
    * spacy.lang.de.German
    * spacy.lang.el.Greek
    * spacy.lang.en.English
    * spacy.lang.es.Spanish
    * spacy.lang.et.Estonian
    * spacy.lang.eu.Basque
    * spacy.lang.fa.Persian
    * spacy.lang.fi.Finnish
    * spacy.lang.fr.French
    * spacy.lang.ga.Irish
    * spacy.lang.grc.AncientGreek
    * spacy.lang.gu.Gujarati
    * spacy.lang.he.Hebrew
    * spacy.lang.hi.Hindi
    * spacy.lang.hr.Croatian
    * spacy.lang.hu.Hungarian
    * spacy.lang.hy.Armenian
    * spacy.lang.id.Indonesian
    * spacy.lang.is.Icelandic
    * spacy.lang.it.Italian
    * spacy.lang.ja.Japanese
    * spacy.lang.kn.Kannada
    * spacy.lang.ko.Korean
    * spacy.lang.ky.Kyrgyz
    * spacy.lang.lb.Luxembourgish
    * spacy.lang.lij.Ligurian
    * spacy.lang.lt.Lithuanian
    * spacy.lang.lv.Latvian
    * spacy.lang.mk.Macedonian
    * spacy.lang.ml.Malayalam
    * spacy.lang.mr.Marathi
    * spacy.lang.nb.Norwegian
    * spacy.lang.ne.Nepali
    * spacy.lang.nl.Dutch
    * spacy.lang.pl.Polish
    * spacy.lang.pt.Portuguese
    * spacy.lang.ro.Romanian
    * spacy.lang.ru.Russian
    * spacy.lang.sa.Sanskrit
    * spacy.lang.si.Sinhala
    * spacy.lang.sk.Slovak
    * spacy.lang.sl.Slovenian
    * spacy.lang.sq.Albanian
    * spacy.lang.sr.Serbian
    * spacy.lang.sv.Swedish
    * spacy.lang.ta.Tamil
    * spacy.lang.te.Telugu
    * spacy.lang.th.Thai
    * spacy.lang.ti.Tigrinya
    * spacy.lang.tl.Tagalog
    * spacy.lang.tn.Setswana
    * spacy.lang.tr.Turkish
    * spacy.lang.tt.Tatar
    * spacy.lang.uk.Ukrainian
    * spacy.lang.ur.Urdu
    * spacy.lang.vi.Vietnamese
    * spacy.lang.xx.MultiLanguage
    * spacy.lang.yo.Yoruba
    * spacy.lang.zh.Chinese

    ### Class variables

    `Defaults`
    :   Language data defaults, available via Language.Defaults. Can be
        overwritten by language subclasses by defining their own subclasses of
        Language.Defaults.

    `default_config`
    :

    `factories`
    :

    `lang: Optional[str]`
    :

    ### Static methods

    `component(name: str, *, assigns: Iterable[str] = [], requires: Iterable[str] = [], retokenizes: bool = False, func: Optional[ForwardRef('Pipe')] = None) ‑> Callable[..., Any]`
    :   Register a new pipeline component. Can be used for stateless function
        components that don't require a separate factory. Can be used as a
        decorator on a function or classmethod, or called as a function with the
        factory provided as the func keyword argument. To create a component and
        add it to the pipeline, you can use nlp.add_pipe(name).
        
        name (str): The name of the component factory.
        assigns (Iterable[str]): Doc/Token attributes assigned by this component,
            e.g. "token.ent_id". Used for pipeline analysis.
        requires (Iterable[str]): Doc/Token attributes required by this component,
            e.g. "token.ent_id". Used for pipeline analysis.
        retokenizes (bool): Whether the component changes the tokenization.
            Used for pipeline analysis.
        func (Optional[Callable]): Factory function if not used as a decorator.
        
        DOCS: https://spacy.io/api/language#component

    `factory(name: str, *, default_config: Dict[str, Any] = {}, assigns: Iterable[str] = [], requires: Iterable[str] = [], retokenizes: bool = False, default_score_weights: Dict[str, Optional[float]] = {}, func: Optional[Callable] = None) ‑> Callable`
    :   Register a new pipeline component factory. Can be used as a decorator
        on a function or classmethod, or called as a function with the factory
        provided as the func keyword argument. To create a component and add
        it to the pipeline, you can use nlp.add_pipe(name).
        
        name (str): The name of the component factory.
        default_config (Dict[str, Any]): Default configuration, describing the
            default values of the factory arguments.
        assigns (Iterable[str]): Doc/Token attributes assigned by this component,
            e.g. "token.ent_id". Used for pipeline analysis.
        requires (Iterable[str]): Doc/Token attributes required by this component,
            e.g. "token.ent_id". Used for pipeline analysis.
        retokenizes (bool): Whether the component changes the tokenization.
            Used for pipeline analysis.
        default_score_weights (Dict[str, Optional[float]]): The scores to report during
            training, and their default weight towards the final score used to
            select the best model. Weights should sum to 1.0 per component and
            will be combined and normalized for the whole pipeline. If None,
            the score won't be shown in the logs or be weighted.
        func (Optional[Callable]): Factory function if not used as a decorator.
        
        DOCS: https://spacy.io/api/language#factory

    `from_config(config: Union[Dict[str, Any], thinc.config.Config] = {}, *, vocab: Union[spacy.vocab.Vocab, bool] = True, disable: Iterable[str] = [], exclude: Iterable[str] = [], meta: Dict[str, Any] = {}, auto_fill: bool = True, validate: bool = True) ‑> spacy.language.Language`
    :   Create the nlp object from a loaded config. Will set up the tokenizer
        and language data, add pipeline components etc. If no config is provided,
        the default config of the given language is used.
        
        config (Dict[str, Any] / Config): The loaded config.
        vocab (Vocab): A Vocab object. If True, a vocab is created.
        disable (Iterable[str]): Names of pipeline components to disable.
            Disabled pipes will be loaded but they won't be run unless you
            explicitly enable them by calling nlp.enable_pipe.
        exclude (Iterable[str]): Names of pipeline components to exclude.
            Excluded components won't be loaded.
        meta (Dict[str, Any]): Meta overrides for nlp.meta.
        auto_fill (bool): Automatically fill in missing values in config based
            on defaults and function argument annotations.
        validate (bool): Validate the component config and arguments against
            the types expected by the factory.
        RETURNS (Language): The initialized Language class.
        
        DOCS: https://spacy.io/api/language#from_config

    `get_factory_meta(name: str) ‑> spacy.language.FactoryMeta`
    :   Get the meta information for a given factory name.
        
        name (str): The component factory name.
        RETURNS (FactoryMeta): The meta for the given factory name.

    `get_factory_name(name: str) ‑> str`
    :   Get the internal factory name based on the language subclass.
        
        name (str): The factory name.
        RETURNS (str): The internal factory name.

    `has_factory(name: str) ‑> bool`
    :   RETURNS (bool): Whether a factory of that name is registered.

    `set_factory_meta(name: str, value: FactoryMeta) ‑> None`
    :   Set the meta information for a given factory name.
        
        name (str): The component factory name.
        value (FactoryMeta): The meta to set.

    ### Instance variables

    `component_names: List[str]`
    :   Get the names of the available pipeline components. Includes all
        active and inactive pipeline components.
        
        RETURNS (List[str]): List of component name strings, in order.

    `components: List[Tuple[str, Pipe]]`
    :   Get all (name, component) tuples in the pipeline, including the
        currently disabled components.

    `config: thinc.config.Config`
    :   Trainable config for the current language instance. Includes the
        current pipeline components, as well as default training config.
        
        RETURNS (thinc.api.Config): The config.
        
        DOCS: https://spacy.io/api/language#config

    `disabled: List[str]`
    :   Get the names of all disabled components.
        
        RETURNS (List[str]): The disabled components.

    `factory_names: List[str]`
    :   Get names of all available factories.
        
        RETURNS (List[str]): The factory names.

    `meta: Dict[str, Any]`
    :   Custom meta data of the language class. If a model is loaded, this
        includes details from the model's meta.json.
        
        RETURNS (Dict[str, Any]): The meta.
        
        DOCS: https://spacy.io/api/language#meta

    `path`
    :

    `pipe_factories: Dict[str, str]`
    :   Get the component factories for the available pipeline components.
        
        RETURNS (Dict[str, str]): Factory names, keyed by component names.

    `pipe_labels: Dict[str, List[str]]`
    :   Get the labels set by the pipeline components, if available (if
        the component exposes a labels property and the labels are not
        hidden).
        
        RETURNS (Dict[str, List[str]]): Labels keyed by component name.

    `pipe_names: List[str]`
    :   Get names of available active pipeline components.
        
        RETURNS (List[str]): List of component name strings, in order.

    `pipeline: List[Tuple[str, Pipe]]`
    :   The processing pipeline consisting of (name, component) tuples. The
        components are called on the Doc in order as it passes through the
        pipeline.
        
        RETURNS (List[Tuple[str, Pipe]]): The pipeline.

    ### Methods

    `add_pipe(self, factory_name: str, name: Optional[str] = None, *, before: Union[str, int, None] = None, after: Union[str, int, None] = None, first: Optional[bool] = None, last: Optional[bool] = None, source: Optional[ForwardRef('Language')] = None, config: Dict[str, Any] = {}, raw_config: Optional[thinc.config.Config] = None, validate: bool = True) ‑> Pipe`
    :   Add a component to the processing pipeline. Valid components are
        callables that take a `Doc` object, modify it and return it. Only one
        of before/after/first/last can be set. Default behaviour is "last".
        
        factory_name (str): Name of the component factory.
        name (str): Name of pipeline component. Overwrites existing
            component.name attribute if available. If no name is set and
            the component exposes no name attribute, component.__name__ is
            used. An error is raised if a name already exists in the pipeline.
        before (Union[str, int]): Name or index of the component to insert new
            component directly before.
        after (Union[str, int]): Name or index of the component to insert new
            component directly after.
        first (bool): If True, insert component first in the pipeline.
        last (bool): If True, insert component last in the pipeline.
        source (Language): Optional loaded nlp object to copy the pipeline
            component from.
        config (Dict[str, Any]): Config parameters to use for this component.
            Will be merged with default config, if available.
        raw_config (Optional[Config]): Internals: the non-interpolated config.
        validate (bool): Whether to validate the component config against the
            arguments and types expected by the factory.
        RETURNS (Pipe): The pipeline component.
        
        DOCS: https://spacy.io/api/language#add_pipe

    `analyze_pipes(self, *, keys: List[str] = ['assigns', 'requires', 'scores', 'retokenizes'], pretty: bool = False) ‑> Optional[Dict[str, Any]]`
    :   Analyze the current pipeline components, print a summary of what
        they assign or require and check that all requirements are met.
        
        keys (List[str]): The meta values to display in the table. Corresponds
            to values in FactoryMeta, defined by @Language.factory decorator.
        pretty (bool): Pretty-print the results.
        RETURNS (dict): The data.

    `begin_training(self, get_examples: Optional[Callable[[], Iterable[spacy.training.example.Example]]] = None, *, sgd: Optional[thinc.optimizers.Optimizer] = None) ‑> thinc.optimizers.Optimizer`
    :

    `create_optimizer(self)`
    :   Create an optimizer, usually using the [training.optimizer] config.

    `create_pipe(self, factory_name: str, name: Optional[str] = None, *, config: Dict[str, Any] = {}, raw_config: Optional[thinc.config.Config] = None, validate: bool = True) ‑> Pipe`
    :   Create a pipeline component. Mostly used internally. To create and
        add a component to the pipeline, you can use nlp.add_pipe.
        
        factory_name (str): Name of component factory.
        name (Optional[str]): Optional name to assign to component instance.
            Defaults to factory name if not set.
        config (Dict[str, Any]): Config parameters to use for this component.
            Will be merged with default config, if available.
        raw_config (Optional[Config]): Internals: the non-interpolated config.
        validate (bool): Whether to validate the component config against the
            arguments and types expected by the factory.
        RETURNS (Pipe): The pipeline component.
        
        DOCS: https://spacy.io/api/language#create_pipe

    `create_pipe_from_source(self, source_name: str, source: Language, *, name: str) ‑> Tuple[Pipe, str]`
    :   Create a pipeline component by copying it from an existing model.
        
        source_name (str): Name of the component in the source pipeline.
        source (Language): The source nlp object to copy from.
        name (str): Optional alternative name to use in current pipeline.
        RETURNS (Tuple[Callable, str]): The component and its factory name.

    `disable_pipe(self, name: str) ‑> None`
    :   Disable a pipeline component. The component will still exist on
        the nlp object, but it won't be run as part of the pipeline. Does
        nothing if the component is already disabled.
        
        name (str): The name of the component to disable.

    `disable_pipes(self, *names) ‑> spacy.language.DisabledPipes`
    :   Disable one or more pipeline components. If used as a context
        manager, the pipeline will be restored to the initial state at the end
        of the block. Otherwise, a DisabledPipes object is returned, that has
        a `.restore()` method you can use to undo your changes.
        
        This method has been deprecated since 3.0

    `enable_pipe(self, name: str) ‑> None`
    :   Enable a previously disabled pipeline component so it's run as part
        of the pipeline. Does nothing if the component is already enabled.
        
        name (str): The name of the component to enable.

    `evaluate(self, examples: Iterable[spacy.training.example.Example], *, batch_size: Optional[int] = None, scorer: Optional[spacy.scorer.Scorer] = None, component_cfg: Optional[Dict[str, Dict[str, Any]]] = None, scorer_cfg: Optional[Dict[str, Any]] = None) ‑> Dict[str, Any]`
    :   Evaluate a model's pipeline components.
        
        examples (Iterable[Example]): `Example` objects.
        batch_size (Optional[int]): Batch size to use.
        scorer (Optional[Scorer]): Scorer to use. If not passed in, a new one
            will be created.
        component_cfg (dict): An optional dictionary with extra keyword
            arguments for specific components.
        scorer_cfg (dict): An optional dictionary with extra keyword arguments
            for the scorer.
        
        RETURNS (Scorer): The scorer containing the evaluation results.
        
        DOCS: https://spacy.io/api/language#evaluate

    `from_bytes(self, bytes_data: bytes, *, exclude: Iterable[str] = []) ‑> spacy.language.Language`
    :   Load state from a binary string.
        
        bytes_data (bytes): The data to load from.
        exclude (Iterable[str]): Names of components or serialization fields to exclude.
        RETURNS (Language): The `Language` object.
        
        DOCS: https://spacy.io/api/language#from_bytes

    `from_disk(self, path: Union[str, pathlib.Path], *, exclude: Iterable[str] = [], overrides: Dict[str, Any] = {}) ‑> spacy.language.Language`
    :   Loads state from a directory. Modifies the object in place and
        returns it. If the saved `Language` object contains a model, the
        model will be loaded.
        
        path (str / Path): A path to a directory.
        exclude (Iterable[str]): Names of components or serialization fields to exclude.
        RETURNS (Language): The modified `Language` object.
        
        DOCS: https://spacy.io/api/language#from_disk

    `get_pipe(self, name: str) ‑> Pipe`
    :   Get a pipeline component for a given component name.
        
        name (str): Name of pipeline component to get.
        RETURNS (callable): The pipeline component.
        
        DOCS: https://spacy.io/api/language#get_pipe

    `get_pipe_config(self, name: str) ‑> thinc.config.Config`
    :   Get the config used to create a pipeline component.
        
        name (str): The component name.
        RETURNS (Config): The config used to create the pipeline component.

    `get_pipe_meta(self, name: str) ‑> spacy.language.FactoryMeta`
    :   Get the meta information for a given component name.
        
        name (str): The component name.
        RETURNS (FactoryMeta): The meta for the given component name.

    `has_pipe(self, name: str) ‑> bool`
    :   Check if a component name is present in the pipeline. Equivalent to
        `name in nlp.pipe_names`.
        
        name (str): Name of the component.
        RETURNS (bool): Whether a component of the name exists in the pipeline.
        
        DOCS: https://spacy.io/api/language#has_pipe

    `initialize(self, get_examples: Optional[Callable[[], Iterable[spacy.training.example.Example]]] = None, *, sgd: Optional[thinc.optimizers.Optimizer] = None) ‑> thinc.optimizers.Optimizer`
    :   Initialize the pipe for training, using data examples if available.
        
        get_examples (Callable[[], Iterable[Example]]): Optional function that
            returns gold-standard Example objects.
        sgd (Optional[Optimizer]): An optimizer to use for updates. If not
            provided, will be created using the .create_optimizer() method.
        RETURNS (thinc.api.Optimizer): The optimizer.
        
        DOCS: https://spacy.io/api/language#initialize

    `make_doc(self, text: str) ‑> spacy.tokens.doc.Doc`
    :   Turn a text into a Doc object.
        
        text (str): The text to process.
        RETURNS (Doc): The processed doc.

    `pipe(self, texts: Union[Iterable[Union[str, spacy.tokens.doc.Doc]], Iterable[Tuple[Union[str, spacy.tokens.doc.Doc], ~_AnyContext]]], *, as_tuples: bool = False, batch_size: Optional[int] = None, disable: Iterable[str] = [], component_cfg: Optional[Dict[str, Dict[str, Any]]] = None, n_process: int = 1) ‑> Union[Iterator[spacy.tokens.doc.Doc], Iterator[Tuple[spacy.tokens.doc.Doc, ~_AnyContext]]]`
    :   Process texts as a stream, and yield `Doc` objects in order.
        
        texts (Iterable[Union[str, Doc]]): A sequence of texts or docs to
            process.
        as_tuples (bool): If set to True, inputs should be a sequence of
            (text, context) tuples. Output will then be a sequence of
            (doc, context) tuples. Defaults to False.
        batch_size (Optional[int]): The number of texts to buffer.
        disable (List[str]): Names of the pipeline components to disable.
        component_cfg (Dict[str, Dict]): An optional dictionary with extra keyword
            arguments for specific components.
        n_process (int): Number of processors to process texts. If -1, set `multiprocessing.cpu_count()`.
        YIELDS (Doc): Documents in the order of the original text.
        
        DOCS: https://spacy.io/api/language#pipe

    `rehearse(self, examples: Iterable[spacy.training.example.Example], *, sgd: Optional[thinc.optimizers.Optimizer] = None, losses: Optional[Dict[str, float]] = None, component_cfg: Optional[Dict[str, Dict[str, Any]]] = None, exclude: Iterable[str] = []) ‑> Dict[str, float]`
    :   Make a "rehearsal" update to the models in the pipeline, to prevent
        forgetting. Rehearsal updates run an initial copy of the model over some
        data, and update the model so its current predictions are more like the
        initial ones. This is useful for keeping a pretrained model on-track,
        even if you're updating it with a smaller set of examples.
        
        examples (Iterable[Example]): A batch of `Example` objects.
        sgd (Optional[Optimizer]): An optimizer.
        component_cfg (Dict[str, Dict]): Config parameters for specific pipeline
            components, keyed by component name.
        exclude (Iterable[str]): Names of components that shouldn't be updated.
        RETURNS (dict): Results from the update.
        
        EXAMPLE:
            >>> raw_text_batches = minibatch(raw_texts)
            >>> for labelled_batch in minibatch(examples):
            >>>     nlp.update(labelled_batch)
            >>>     raw_batch = [Example.from_dict(nlp.make_doc(text), {}) for text in next(raw_text_batches)]
            >>>     nlp.rehearse(raw_batch)
        
        DOCS: https://spacy.io/api/language#rehearse

    `remove_pipe(self, name: str) ‑> Tuple[str, Pipe]`
    :   Remove a component from the pipeline.
        
        name (str): Name of the component to remove.
        RETURNS (tuple): A `(name, component)` tuple of the removed component.
        
        DOCS: https://spacy.io/api/language#remove_pipe

    `rename_pipe(self, old_name: str, new_name: str) ‑> None`
    :   Rename a pipeline component.
        
        old_name (str): Name of the component to rename.
        new_name (str): New name of the component.
        
        DOCS: https://spacy.io/api/language#rename_pipe

    `replace_listeners(self, tok2vec_name: str, pipe_name: str, listeners: Iterable[str]) ‑> None`
    :   Find listener layers (connecting to a token-to-vector embedding
        component) of a given pipeline component model and replace
        them with a standalone copy of the token-to-vector layer. This can be
        useful when training a pipeline with components sourced from an existing
        pipeline: if multiple components (e.g. tagger, parser, NER) listen to
        the same tok2vec component, but some of them are frozen and not updated,
        their performance may degrade significally as the tok2vec component is
        updated with new data. To prevent this, listeners can be replaced with
        a standalone tok2vec layer that is owned by the component and doesn't
        change if the component isn't updated.
        
        tok2vec_name (str): Name of the token-to-vector component, typically
            "tok2vec" or "transformer".
        pipe_name (str): Name of pipeline component to replace listeners for.
        listeners (Iterable[str]): The paths to the listeners, relative to the
            component config, e.g. ["model.tok2vec"]. Typically, implementations
            will only connect to one tok2vec component, [model.tok2vec], but in
            theory, custom models can use multiple listeners. The value here can
            either be an empty list to not replace any listeners, or a complete
            (!) list of the paths to all listener layers used by the model.
        
        DOCS: https://spacy.io/api/language#replace_listeners

    `replace_pipe(self, name: str, factory_name: str, *, config: Dict[str, Any] = {}, validate: bool = True) ‑> Pipe`
    :   Replace a component in the pipeline.
        
        name (str): Name of the component to replace.
        factory_name (str): Factory name of replacement component.
        config (Optional[Dict[str, Any]]): Config parameters to use for this
            component. Will be merged with default config, if available.
        validate (bool): Whether to validate the component config against the
            arguments and types expected by the factory.
        RETURNS (Pipe): The new pipeline component.
        
        DOCS: https://spacy.io/api/language#replace_pipe

    `resume_training(self, *, sgd: Optional[thinc.optimizers.Optimizer] = None) ‑> thinc.optimizers.Optimizer`
    :   Continue training a pretrained model.
        
        Create and return an optimizer, and initialize "rehearsal" for any pipeline
        component that has a .rehearse() method. Rehearsal is used to prevent
        models from "forgetting" their initialized "knowledge". To perform
        rehearsal, collect samples of text you want the models to retain performance
        on, and call nlp.rehearse() with a batch of Example objects.
        
        RETURNS (Optimizer): The optimizer.
        
        DOCS: https://spacy.io/api/language#resume_training

    `select_pipes(self, *, disable: Union[str, Iterable[str], None] = None, enable: Union[str, Iterable[str], None] = None) ‑> spacy.language.DisabledPipes`
    :   Disable one or more pipeline components. If used as a context
        manager, the pipeline will be restored to the initial state at the end
        of the block. Otherwise, a DisabledPipes object is returned, that has
        a `.restore()` method you can use to undo your changes.
        
        disable (str or iterable): The name(s) of the pipes to disable
        enable (str or iterable): The name(s) of the pipes to enable - all others will be disabled
        
        DOCS: https://spacy.io/api/language#select_pipes

    `set_error_handler(self, error_handler: Callable[[str, ForwardRef('Pipe'), List[spacy.tokens.doc.Doc], Exception], NoReturn])`
    :   Set an error handler object for all the components in the pipeline that implement
        a set_error_handler function.
        
        error_handler (Callable[[str, Pipe, List[Doc], Exception], NoReturn]):
            Function that deals with a failing batch of documents. This callable function should take in
            the component's name, the component itself, the offending batch of documents, and the exception
            that was thrown.
        DOCS: https://spacy.io/api/language#set_error_handler

    `to_bytes(self, *, exclude: Iterable[str] = []) ‑> bytes`
    :   Serialize the current state to a binary string.
        
        exclude (Iterable[str]): Names of components or serialization fields to exclude.
        RETURNS (bytes): The serialized form of the `Language` object.
        
        DOCS: https://spacy.io/api/language#to_bytes

    `to_disk(self, path: Union[str, pathlib.Path], *, exclude: Iterable[str] = []) ‑> None`
    :   Save the current state to a directory.  If a model is loaded, this
        will include the model.
        
        path (str / Path): Path to a directory, which will be created if
            it doesn't exist.
        exclude (Iterable[str]): Names of components or serialization fields to exclude.
        
        DOCS: https://spacy.io/api/language#to_disk

    `update(self, examples: Iterable[spacy.training.example.Example], *, drop: float = 0.0, sgd: Optional[thinc.optimizers.Optimizer] = None, losses: Optional[Dict[str, float]] = None, component_cfg: Optional[Dict[str, Dict[str, Any]]] = None, exclude: Iterable[str] = [], annotates: Iterable[str] = [])`
    :   Update the models in the pipeline.
        
        examples (Iterable[Example]): A batch of examples
        _: Should not be set - serves to catch backwards-incompatible scripts.
        drop (float): The dropout rate.
        sgd (Optimizer): An optimizer.
        losses (Dict[str, float]): Dictionary to update with the loss, keyed by
            component.
        component_cfg (Dict[str, Dict]): Config parameters for specific pipeline
            components, keyed by component name.
        exclude (Iterable[str]): Names of components that shouldn't be updated.
        annotates (Iterable[str]): Names of components that should set
            annotations on the predicted examples after updating.
        RETURNS (Dict[str, float]): The updated losses dictionary
        
        DOCS: https://spacy.io/api/language#update

    `use_params(self, params: Optional[dict])`
    :   Replace weights of models in the pipeline with those provided in the
        params dictionary. Can be used as a contextmanager, in which case,
        models go back to their original weights after the block.
        
        params (dict): A dictionary of parameters keyed by model ID.
        
        EXAMPLE:
            >>> with nlp.use_params(optimizer.averages):
            >>>     nlp.to_disk("/tmp/checkpoint")
        
        DOCS: https://spacy.io/api/language#use_params