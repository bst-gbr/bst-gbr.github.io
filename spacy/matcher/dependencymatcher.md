Module spacy.matcher.dependencymatcher
======================================

Functions
---------

    
`unpickle_matcher(vocab, patterns, callbacks)`
:   

Classes
-------

`DependencyMatcher(...)`
:   DependencyMatcher(vocab, validate=False, *)
    Match dependency parse tree based on pattern rules.
    
    Create the DependencyMatcher.
    
    vocab (Vocab): The vocabulary object, which must be shared with the
        documents the matcher will operate on.
    validate (bool): Whether patterns should be validated, passed to
        Matcher as `validate`

    ### Instance variables

    `vocab`
    :   Return an attribute of instance, which is of type owner.

    ### Methods

    `add(...)`
    :   DependencyMatcher.add(self, key, patterns, *, on_match=None)
        Add a new matcher rule to the matcher.
        
                key (str): The match ID.
                patterns (list): The patterns to add for the given key.
                on_match (callable): Optional callback executed on match.

    `get(...)`
    :   DependencyMatcher.get(self, key, default=None)
        Retrieve the pattern stored for a key.
        
                key (str / int): The key to retrieve.
                RETURNS (tuple): The rule, as an (on_match, patterns) tuple.

    `has_key(...)`
    :   DependencyMatcher.has_key(self, key)
        Check whether the matcher has a rule with a given key.
        
                key (string or int): The key to check.
                RETURNS (bool): Whether the matcher has the rule.

    `remove(...)`
    :   DependencyMatcher.remove(self, key)