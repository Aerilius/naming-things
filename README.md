# Naming Things

## Why it is important to choose meaningful and consistent names:

- Consistent reuse of exact names (and not variants or incomplete names) helps others to identify what is meant and whether two things are the same or slightly different concepts.
- Names that convey meaning serve as self-documention.
- Inconsistency spreads because new people are guided by what is already there.

## Guidelines for choosing names

- Leverage **common conventions** and usage of language:
  - Research which terms are most commonly used elsewhere in the current project or in the world.
    - Does a matching name already exist? Use it.
    - Do related names exist? Follow their pattern:
      - Symmetry (use the opposite of an existing term)
      - Parallelity (form analogs to existing terms by either same root or same prefixes)
  - Take care of correct usage of:
    - `get`: does not perform any work, but accesses and returns something that is already there.
    - `load`/`read`: transforms something that is already there into an in-memory representation.
    - `create`/`generate`: creates something new that is not already there (possibly out of no inputs).
    - `compute`/`calculate`: performs work to transform inputs or a starting state into results.
  - Some further conventions:
    - method names should start with a verb (and lowercase)
    - class names should be nouns (not verbs), and start with a capital letter  
      `Visualization` or `Visualizer`, not `Visualize`

- **Understandability**:

  - **Correctness**: "If it does not a moo, then don't call it a cow."
    - If it is a collection of multiple things, make sure to use plural (s), otherwise use singular.
    - `with open("filename.json", "r") as json_data:`  This is a file pointer, which must be read and loaded as JSON before it actually is the `json_data` that the reader expects. It should rather be named `file` or `f`.
    - `process_data["process_data"]` If the inner object is a input, the outer object certainly is not the same. One of both is misnamed and needs a name that describes what it actually is.

  - **Precision**, **Unambiguity**:
    - The name has a unique meaning and a unique usage:  
      A reader should have no doubts about whether it means one thing or different thing.
    - It does not collide (not same name for different objects):   
      Is there something else to which the same name would fit (name collision).  
      e.g. variable "`code`" (string, HtmlElement), "`constraints`" (list of Constraint, instance of ConstraintCollection, Tensorflow tensor containing computed constraints)
    - It distinguishes an object from other objects (not similar names for dissimilar objects).  
      bad: `process_data`, `proc_data`

  - **Conciseness**:
    - Omit redundant words:  
      If something is self-evident and true for all names, it does not need to be part of the name.  
      e.g. all dataframes were read from Excel files, then variables don't need to be prefixed with "`excel_`"  
    - Avoid meaningless words:
      - `data`, `run`, `processing`
      - `utils`, `helper`, `manager` as part of class names

  - **Shortness**

  - Avoid contractions and abbreviations

- **Order**:

  - **Importance**:
    The most informative part should be at the beginning ↔ Readability: It may not sound like natural language
    - general to specific ↔ specific to general
    - noun – adjectives ↔ adjectives – noun
    - verb – object ([Polish notation](https://en.wikipedia.org/wiki/Polish_notation)) a object ↔ verb ([Reverse Polish notation](https://en.wikipedia.org/wiki/Reverse_Polish_notation))

  - **Alphanumerical** sorting:
    - Related things should still remain grouped after sorting.
    - Use leading zeros for numbers (to avoid `01, 02, 10…` instead of `1, 10, 2…`)

- **Restrictions**:

  - Consider forbidden or unsupported characters on some file systems (special characters, file path separators)
  - Valid identifier in a programming language (e.g. when importing a directory as python package, then it should have underscores and no hyphens or spaces)
  - Easier selection: no spaces


---

TODO: Trim down the rules into 3 rememberable keywords/questions to easily assess whether a name is good or not.

---

## References

References used to develop this guide:

<https://en.wikipedia.org/wiki/Naming_convention_(programming)#Potential_benefits>

<https://de.slideshare.net/milkers/naming-things>

<https://en.rmcreative.ru/blog/naming-things/>