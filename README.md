# relational-implication-dataset

This repository contains the dataset first described in 'Probabilistic Models of Relational Implication'.

### Format

Each line represents an implication rule between (partially) instantiated propositions. The implication `wrote(PERSON, BOOK) -> written_by(BOOK, PERSON)` would be represented as:

```
PERSON, wrote, BOOK\tBOOK, written_by, PERSON\tTrue
```

And the negative implication rule `wrote(PERSON, BOOK) -\> enjoyed_writing(PERSON, BOOK)` would be represented as:

```
PERSON, wrote, BOOK\tPERSON, enjoyed_writing, BOOK\tFalse
```

### Files

* 'Probabilistic Models of Relational Implication.pdf': The thesis describing this dataset.
* 'implications.tsv': Implications where instantiating arguments have been genericised e.g. 'ephedrine' would become 'DRUG'. Duplicate entries resulting from this genericisation have been removed. This was the representation over which the crowd workers annotated.
* 'directional_implications.tsv': Implications that only occur strictly in one direction, that is, `p(_, _) -> q(_, _)` but `q(_, _) -\> p(_, _)` or vice-versa. A label of `True` indicates that the implication occurs from left-to-right, a label of `False` indicates the implication occurs from right-to-left.
* 'implications_instantiated.tsv': The fully instantiated implication rules. These have mainly been included for compatibility/comparison with the original Levy et al. dataset.
