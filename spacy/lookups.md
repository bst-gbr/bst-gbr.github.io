Module spacy.lookups
====================

Functions
---------

    
`load_lookups(lang: str, tables: List[str], strict: bool = True) ‑> spacy.lookups.Lookups`
:   Load the data from the spacy-lookups-data package for a given language,
    if available. Returns an empty `Lookups` container if there's no data or if the package
    is not installed.
    
    lang (str): The language code (corresponds to entry point exposed by
        the spacy-lookups-data package).
    tables (List[str]): Name of tables to load, e.g. ["lemma_lookup", "lemma_exc"]
    strict (bool): Whether to raise an error if a table doesn't exist.
    RETURNS (Lookups): The lookups container containing the loaded tables.

Classes
-------

`Lookups()`
:   Container for large lookup tables and dictionaries, e.g. lemmatization
    data or tokenizer exception lists. Lookups are available via vocab.lookups,
    so they can be accessed before the pipeline components are applied (e.g.
    in the tokenizer and lemmatizer), as well as within the pipeline components
    via doc.vocab.lookups.
    
    Initialize the Lookups object.
    
    DOCS: https://spacy.io/api/lookups#init

    ### Instance variables

    `tables: List[str]`
    :   RETURNS (List[str]): Names of all tables in the lookups.

    ### Methods

    `add_table(self, name: str, data: dict = {}) ‑> spacy.lookups.Table`
    :   Add a new table to the lookups. Raises an error if the table exists.
        
        name (str): Unique name of table.
        data (dict): Optional data to add to the table.
        RETURNS (Table): The newly added table.
        
        DOCS: https://spacy.io/api/lookups#add_table

    `from_bytes(self, bytes_data: bytes, **kwargs) ‑> spacy.lookups.Lookups`
    :   Load the lookups from a bytestring.
        
        bytes_data (bytes): The data to load.
        RETURNS (Lookups): The loaded Lookups.
        
        DOCS: https://spacy.io/api/lookups#from_bytes

    `from_disk(self, path: Union[str, pathlib.Path], filename: str = 'lookups.bin', **kwargs) ‑> spacy.lookups.Lookups`
    :   Load lookups from a directory containing a lookups.bin. Will skip
        loading if the file doesn't exist.
        
        path (str / Path): The directory path.
        RETURNS (Lookups): The loaded lookups.
        
        DOCS: https://spacy.io/api/lookups#from_disk

    `get_table(self, name: str, default: Any = <object object>) ‑> spacy.lookups.Table`
    :   Get a table. Raises an error if the table doesn't exist and no
        default value is provided.
        
        name (str): Name of the table.
        default (Any): Optional default value to return if table doesn't exist.
        RETURNS (Table): The table.
        
        DOCS: https://spacy.io/api/lookups#get_table

    `has_table(self, name: str) ‑> bool`
    :   Check if the lookups contain a table of a given name.
        
        name (str): Name of the table.
        RETURNS (bool): Whether a table of that name exists.
        
        DOCS: https://spacy.io/api/lookups#has_table

    `remove_table(self, name: str) ‑> spacy.lookups.Table`
    :   Remove a table. Raises an error if the table doesn't exist.
        
        name (str): Name of the table to remove.
        RETURNS (Table): The removed table.
        
        DOCS: https://spacy.io/api/lookups#remove_table

    `set_table(self, name: str, table: spacy.lookups.Table) ‑> None`
    :   Set a table.
        
        name (str): Name of the table to set.
        table (Table): The Table to set.
        
        DOCS: https://spacy.io/api/lookups#set_table

    `to_bytes(self, **kwargs) ‑> bytes`
    :   Serialize the lookups to a bytestring.
        
        RETURNS (bytes): The serialized Lookups.
        
        DOCS: https://spacy.io/api/lookups#to_bytes

    `to_disk(self, path: Union[str, pathlib.Path], filename: str = 'lookups.bin', **kwargs) ‑> None`
    :   Save the lookups to a directory as lookups.bin. Expects a path to a
        directory, which will be created if it doesn't exist.
        
        path (str / Path): The file path.
        
        DOCS: https://spacy.io/api/lookups#to_disk

`Table(name: Optional[str] = None, data: Optional[dict] = None)`
:   A table in the lookups. Subclass of builtin dict that implements a
    slightly more consistent and unified API.
    
    Includes a Bloom filter to speed up missed lookups.
    
    Initialize a new table.
    
    name (str): Optional table name for reference.
    data (dict): Initial data, used to hint Bloom Filter.
    
    DOCS: https://spacy.io/api/lookups#table.init

    ### Ancestors (in MRO)

    * collections.OrderedDict
    * builtins.dict

    ### Static methods

    `from_dict(data: dict, name: Optional[str] = None) ‑> spacy.lookups.Table`
    :   Initialize a new table from a dict.
        
        data (dict): The dictionary.
        name (str): Optional table name for reference.
        
        DOCS: https://spacy.io/api/lookups#table.from_dict

    ### Methods

    `from_bytes(self, bytes_data: bytes) ‑> spacy.lookups.Table`
    :   Load a table from a bytestring.
        
        bytes_data (bytes): The data to load.
        RETURNS (Table): The loaded table.
        
        DOCS: https://spacy.io/api/lookups#table.from_bytes

    `get(self, key: Union[str, int], default: Optional[Any] = None) ‑> Any`
    :   Get the value for a given key. String keys will be hashed.
        
        key (str / int): The key to get.
        default: The default value to return.
        RETURNS: The value.

    `set(self, key: Union[str, int], value: Any) ‑> None`
    :   Set new key/value pair. String keys will be hashed.
        Same as table[key] = value.
        
        key (str / int): The key to set.
        value: The value to set.

    `to_bytes(self) ‑> bytes`
    :   Serialize table to a bytestring.
        
        RETURNS (bytes): The serialized table.
        
        DOCS: https://spacy.io/api/lookups#table.to_bytes