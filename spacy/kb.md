Module spacy.kb
===============

Functions
---------

    
`get_candidates(...)`
:   get_candidates(KnowledgeBase kb, span) -> Iterator[Candidate]
    
    Return candidate entities for a given span by using the text of the span as the alias
    and fetching appropriate entries from the index.
    This particular function is optimized to work with the built-in KB functionality,
    but any other custom candidate generation method can be used in combination with the KB as well.

Classes
-------

`Candidate(*args, **kwargs)`
:   Candidate(KnowledgeBase kb, entity_hash, entity_freq, entity_vector, alias_hash, prior_prob)
    A `Candidate` object refers to a textual mention (`alias`) that may or may not be resolved
        to a specific `entity` from a Knowledge Base. This will be used as input for the entity linking
        algorithm which will disambiguate the various candidates to the correct one.
        Each candidate (alias, entity) pair is assigned to a certain prior probability.
    
        DOCS: https://spacy.io/api/kb/#candidate_init

    ### Instance variables

    `alias`
    :   RETURNS (uint64): hash of the alias

    `alias_`
    :   RETURNS (str): ID of the original alias

    `entity`
    :   RETURNS (uint64): hash of the entity's KB ID/name

    `entity_`
    :   RETURNS (str): ID/name of this entity in the KB

    `entity_freq`
    :   Return an attribute of instance, which is of type owner.

    `entity_vector`
    :   Return an attribute of instance, which is of type owner.

    `kb`
    :   Return an attribute of instance, which is of type owner.

    `prior_prob`
    :   Return an attribute of instance, which is of type owner.

`KnowledgeBase(...)`
:   KnowledgeBase(Vocab vocab, entity_vector_length)
    A `KnowledgeBase` instance stores unique identifiers for entities and their textual aliases,
        to support entity linking of named entities to real-world concepts.
    
        DOCS: https://spacy.io/api/kb
        
    
    Create a KnowledgeBase.

    ### Instance variables

    `entity_vector_length`
    :   RETURNS (uint64): length of the entity vectors

    `vocab`
    :   Return an attribute of instance, which is of type owner.

    ### Methods

    `add_alias(...)`
    :   KnowledgeBase.add_alias(self, str alias, entities, probabilities)
        
        For a given alias, add its potential entities and prior probabilies to the KB.
        Return the alias_hash at the end

    `add_entity(...)`
    :   KnowledgeBase.add_entity(self, str entity, float freq, vector[float] entity_vector)
        
        Add an entity to the KB, optionally specifying its log probability based on corpus frequency
        Return the hash of the entity ID/name at the end.

    `append_alias(...)`
    :   KnowledgeBase.append_alias(self, str alias, str entity, float prior_prob, ignore_warnings=False)
        
        For an alias already existing in the KB, extend its potential entities with one more.
        Throw a warning if either the alias or the entity is unknown,
        or when the combination is already previously recorded.
        Throw an error if this entity+prior prob would exceed the sum of 1.
        For efficiency, it's best to use the method `add_alias` as much as possible instead of this one.

    `contains_alias(...)`
    :   KnowledgeBase.contains_alias(self, str alias)

    `contains_entity(...)`
    :   KnowledgeBase.contains_entity(self, str entity)

    `from_bytes(...)`
    :   KnowledgeBase.from_bytes(self, bytes_data, *, exclude=tuple())
        Load state from a binary string.

    `from_disk(...)`
    :   KnowledgeBase.from_disk(self, path, exclude: Iterable[str] = SimpleFrozenList())

    `get_alias_candidates(...)`
    :   KnowledgeBase.get_alias_candidates(self, str alias) -> Iterator[Candidate]
        
        Return candidate entities for an alias. Each candidate defines the entity, the original alias,
        and the prior probability of that alias resolving to that entity.
        If the alias is not known in the KB, and empty list is returned.

    `get_alias_strings(...)`
    :   KnowledgeBase.get_alias_strings(self)

    `get_entity_strings(...)`
    :   KnowledgeBase.get_entity_strings(self)

    `get_prior_prob(...)`
    :   KnowledgeBase.get_prior_prob(self, str entity, str alias)
        Return the prior probability of a given alias being linked to a given entity,
               or return 0.0 when this combination is not known in the knowledge base

    `get_size_aliases(...)`
    :   KnowledgeBase.get_size_aliases(self)

    `get_size_entities(...)`
    :   KnowledgeBase.get_size_entities(self)

    `get_vector(...)`
    :   KnowledgeBase.get_vector(self, str entity)

    `initialize_aliases(...)`
    :   KnowledgeBase.initialize_aliases(self, int64_t nr_aliases)

    `initialize_entities(...)`
    :   KnowledgeBase.initialize_entities(self, int64_t nr_entities)

    `initialize_vectors(...)`
    :   KnowledgeBase.initialize_vectors(self, int64_t nr_entities)

    `read_contents(...)`
    :   KnowledgeBase.read_contents(self, file_path)

    `set_entities(...)`
    :   KnowledgeBase.set_entities(self, entity_list, freq_list, vector_list)

    `to_bytes(...)`
    :   KnowledgeBase.to_bytes(self, **kwargs)
        Serialize the current state to a binary string.

    `to_disk(...)`
    :   KnowledgeBase.to_disk(self, path, exclude: Iterable[str] = SimpleFrozenList())

    `write_contents(...)`
    :   KnowledgeBase.write_contents(self, file_path)

`Reader(*args, **kwargs)`
:   Reader(path)

`Writer(*args, **kwargs)`
:   Writer(path)

    ### Methods

    `close(...)`
    :   Writer.close(self)