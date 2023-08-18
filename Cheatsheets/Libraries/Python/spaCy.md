## Installation

```bash
# https://spacy.io/usage
pip install -U pip setuptools wheel
pip install -U spacy
python -m spacy download en_core_web_sm # Model (Optional)
```

When using pip it is generally recommended to install packages in a virtual environment to avoid modifying system state:

```bash
python -m venv .env
source .env/bin/activate
pip install -U pip setuptools wheel
pip install -U spacy
```

# Basic

## Usage

```python  
import spacy

# Load a language model
nlp = spacy.load("en_core_web_sm")

# Process text
text = "This is an example sentence."
doc = nlp(text)

# Tokenization
for token in doc:
    print(token.text, token.pos_, token.dep_)

# Named Entity Recognition (NER)
for ent in doc.ents:
    print(ent.text, ent.label_) # ent.label would produce an integer

# Part-of-Speech Tagging
for token in doc:
    print(token.text, token.pos_)
```

## Lemmatization

```python  
# Lemmatization
for token in doc:
    print(token.text, token.lemma_)
```

## Dependency Parsing

```python  
# Dependency parsing
for token in doc:
    print(token.text, token.dep_, token.head.text)
```

## Stop Words

```python  
# Check if a token is a stop word
for token in doc:
    if token.is_stop:
        print(token.text)
```

## Customization

```python  
# Adding a stop word
nlp.Defaults.stop_words.add("example")

# Adding a rule-based component
from spacy.pipeline import EntityRuler

ruler = EntityRuler(nlp)
ruler.add_patterns([{"label": "ORG", "pattern": "SpaCy"}])
nlp.add_pipe(ruler)
```

## Word Vectors

```python  
# Word vectors
token = doc[1]
print(token.text, token.vector)
```

## Similarity

```python  
# Token similarity
token1 = doc[0]
token2 = doc[3]
similarity = token1.similarity(token2)
print(similarity)
```

## Language Features

```python  
# Check if a word has a vector
word_has_vector = nlp.vocab.has_vector("example")
print(word_has_vector)
```

## Entity Linking (Experimental)

```python  
# Entity linking (experimental)
for ent in doc.ents:
    if ent.kb_id_:
        print(ent.text, ent.kb_id_)
```

## Disabling Components

```python  
# Disable specific pipeline components
nlp.disable_pipe("ner")
```

## Part-of-Speech Tag Descriptions

- ADJ: adjective
- NOUN: noun
- VERB: verb
- ADV: adverb
- ...

## Dependency Labels

- nsubj: nominal subject
- dobj: direct object
- prep: prepositional modifier
- ...

## Entity Labels

- ORG: organization
- PERSON: person
- DATE: date
- ...

# Advanced

## Custom Pipelines

```python
import spacy

def custom_pipeline(doc):
    # Custom processing
    return doc

nlp = spacy.load("en_core_web_sm")
nlp.add_pipe(custom_pipeline, name="custom", last=True)
```

## Rule-Based Matching

```python  
from spacy.matcher import Matcher

matcher = Matcher(nlp.vocab)
pattern = [{"LOWER": "example"}]
matcher.add("example_pattern", [pattern])

doc = nlp("This is an example sentence.")
matches = matcher(doc)
for match_id, start, end in matches:
    matched_span = doc[start:end]
    print(matched_span.text)
```

## Text Classification

```python  
import spacy
from spacy.pipeline.textcat import single_label_cnn_config

nlp = spacy.load("en_core_web_sm")
textcat = nlp.add_pipe("textcat", config=single_label_cnn_config())
textcat.add_label("POSITIVE")

train_data = [("Text to classify", {"cats": {"POSITIVE": 1}})]
textcat.pipe_names

textcat.update(train_data)
doc = nlp("Text to classify")
print(doc.cats)
```

## Word Embeddings

```python  
import spacy

nlp = spacy.load("en_core_web_md")
token = nlp("example")[0]
print(token.vector)
```

## Knowledge Base Integration

```python  
from spacy.kb import KnowledgeBase

kb = KnowledgeBase(vocab=nlp.vocab)
kb.load_bulk("kb_file.tsv")

nlp.add_pipe("entity_linker", config={"kb": kb})
```

## Named Entity Recognition (NER) Customization

```python  
from spacy.training.example import Example

def train_ner(nlp, train_data):
    for text, annotations in train_data:
        doc = nlp.make_doc(text)
        example = Example.from_dict(doc, annotations)
        nlp.update([example], drop=0.5)
```

## Multilingual NLP

```python  
import spacy

nlp_en = spacy.load("en_core_web_sm")
nlp_de = spacy.load("de_core_news_sm")

doc_en = nlp_en("This is an English sentence.")
doc_de = nlp_de("Das ist ein deutscher Satz.")
```

## Dependency Parsing Visualization

```python  
from spacy import displacy

doc = nlp("This is an example sentence.")
displacy.render(doc, style="dep", options={"compact": True})
```

## spaCy Project Templates

```bash  
python -m spacy project clone base_path
python -m spacy project run train
python -m spacy project run evaluate
```

## Advanced Language Features

```python  
# Accessing word vectors
vector = nlp.vocab.get_vector("example")

# Accessing word frequency
freq = nlp.vocab.get_lexeme("example").count

# Accessing linguistic features
pos = nlp.vocab["example"].morph.to_dict()["POS"]
```

>[!Note]
>Please note that this cheat-sheet provides an advanced overview of spaCy's capabilities. For more detailed information and specific use cases, refer to the official documentation, courses, and tutorials provided by the spaCy team.

---

## References

- Official spaCy Documentation: [https://spacy.io/docs/usage/](https://spacy.io/docs/usage/)
- spaCy Models: [https://spacy.io/models/](https://spacy.io/models/)