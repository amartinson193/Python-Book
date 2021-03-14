# Python-Book

https://amartinson193.github.io/Python-Book

# 2021-3-13

\w

* This is a character, \w+ are words 

r before a string tells Python to interpret the string as a raw string and ignore any special characters such as a backslash

-- 3:09pm @ Intro to Tokenization

## Tokenization

* Breaking text into smaller chunks using regex



## nltk

* The pattern comes second, after string, which is the reverse of the re library
* Typically used to tokenize
* E.g.

```
from nltk.tokenize import word_tokenize
word_tokenize('Hi there!')
```                        

* Other nltk tokenizers
    * sent_tokenize
        * tokenize a document into sentences
    * regexp_tokenize   
        * tokenize a string or doc based on a regex pattern
    * TweetTokenizer
        * special class just for tweet tokenization
        * This is a class method
            * Has a tokenize instance method
            * e.g.

```
tknzr = TweetTokenizer(tweets)
all_tokens = [tknzr.tokenize(t) for t in tweets]
print(all_tokens)
```

```
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenizer

text = """The cat is in the box. The cat likes the box. The box is over the cat."""
tokens = [w for w in word_tokenize(text.lower()) if w.isalpha()]
no_stops = [t for t in token if t not in stopwords.words('english')]
```

* This is a new class method that contains stop words
    * Stop words are words you would like to exclude

```
from ntlk.stem import wordnet_lemmatizer
```

* This is a class method for stemming (shortening) words


nltk documentation

* https://www.nltk.org/
* Here is a book: https://www.nltk.org/book/

#### How to perform NER in ntlk

```
tokenized_sent = nltk.word_tokenize(sentence)
tagged_sent = nltk.pos_tag(tokenized_sent)
ntlk.ne_chunk(tagged_sent)
```

* nltk.pos_tag
    * identifies parts of speech i.e. proper noun, pronoun, adjective, etc...
* ntlk.ne_chunk
    * named entity chunk - returns sentence as a tree
* nltk.ne_chunk_sents


## re package

* re.start(), re.end()
    * These retrun the start and end indices of your match

* |
    * or in regex
* define a group using ()
* character ranges are defined using []        

* Unicode ranges for emoji are:
* ('\U0001F300'-'\U0001F5FF'), ('\U0001F600-\U0001F64F'), ('\U0001F680-\U0001F6FF'), and ('\u2600'-\u26FF-\u2700-\u27BF').

```
emoji = "['\U0001F300-\U0001F5FF'|'\U0001F600-\U0001F64F'|'\U0001F680-\U0001F6FF'|'\u2600-\u26FF\u2700-\u27BF']"
```        

* Bag of words
    * Counts up all the words and orders them by frequency, the largest is considered the most important

## Collections Package

* Counter
    * This function creates a dictionary of counts, seems similar to value_counts in pandas
    * Class method
        * Instance method is most_common(int)
            * It takes the number of most common you want to see
* defaultdict
    * Example: https://www.geeksforgeeks.org/defaultdict-in-python/
    * When the int class is passed as the default_factory argument, then a defaultdict is created with default value as zero.



## Preprocess

* Lemmiatization/Stemming
    * Shortening the words to their root stems
* Lowercasing words
* Plural words to singular
* Negation detection is an important preprocessing step
    * Source: Tools and Approaches to NLP in Clinical Notes - Wiki@UCSF 
* Misspellings

## Genism

* Helps you build bag of word dictionaries for multiple documents
* Word vector
    * Multi-dimensional representation of a word
* LDA

```
from gensim.corpora.dictionary import Dictionary

dictionary = Dictionary(tokenized_docs)

corpus = [dictionary.doc2bow(doc) for doc in tokenized docs] 
```

* Dictionary class method
    * Takes some tokenized documents and creates a dictionary
    * doc2bow instance method

* token2id
    * Dictionary instance method
    * Retrieves ID for token
    * Was used with .get after the instance call to get the word wanted

```
from gensim.models.tfidfmodel import TfifModel
tfidf = TfidfModel(corpus)
tfidf[corpus[1]]

# Calculate the tfidf weights of doc: tfidf_weights
tfidf_weights = tfidf[doc]
```        

* The above is how to incorporate a tfidf model in gensim        


## itertools

* itertools.chain.from_iterable
    * itertools.chain.from_iterable() allows us to iterate through a set of sequences as if they were one continuous sequence. Using this function, we can easily iterate through our corpus object (which is a list of lists).
        * Recursive iteration

## TF-IDF

* Stands for term-frequency - inverse document frequency    
* Helps determine most important words in the document
* Corpus could have words shared across documents and these are down-weighted in importance

## Named Entity Recognition

* What is named-entity-recognition?
    * This is recognizing names of proper things like people, organizations, etc...
    * Wikipedia
        * https://en.wikipedia.org/wiki/Named-entity_recognition
    * https://towardsdatascience.com/named-entity-recognition-with-nltk-and-spacy-8c4a7d88e7da


## Other


* Corpora
    * Set of documents used to perform an NLP task
* Sorting a dictionary

```        
sorted_word_count = sorted(total_word_count.items(), key=lambda w: w[1], reverse=True) 
```

* Hasattr function        
