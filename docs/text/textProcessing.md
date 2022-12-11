# About Text Processing
Text processing is a fundamental part of natural language processing (NLP), and refers to the process of analyzing and manipulating text data in order to extract useful information. This typically involves a combination of techniques, including tokenization, stemming, lemmatization, and part-of-speech tagging. The goal of text processing is to convert raw text into a structured format that is easier for NLP algorithms to work with, and to extract important information such as named entities, relationships, and sentiment. Text processing is an essential step in many NLP tasks, and is often the starting point for more advanced techniques such as text classification, summarization, and translation.
By ChatGPT

## What do we want to treat as a “WORD”?
In natural language processing (NLP), the concept of a "word" can be somewhat subjective and open to interpretation. Generally, a word is defined as a sequence of characters that constitutes a unit of meaning, and can be used to convey a specific idea or concept. However, different NLP algorithms and applications may have different criteria for what constitutes a word, and may treat different sequences of characters as words depending on the specific context and task. For example, some algorithms might treat numbers and punctuation marks as separate words, while others might ignore them or treat them differently. Ultimately, the definition of a "word" in NLP depends on the specific needs and goals of the application, and may vary depending on the context and task at hand.
By ChatGPT


By Source:

- We need to decide
    * What is a minimal unit (token) within a document or a text corpus
    * Which tokens to keep for a particular application, and which to remove
- Each word and each punctuation mark are typically separate tokens
    * Punctuation marks can help identify boundaries of sentences, aspects of meaning (e.g., question vs. statement)
- Sometimes parts of words are also tokens
    * E.g., “uh” and “main-“ in the following (spoken) utterance: “I do uh main- mainly business data processing”

## What is Inflection?

Inflection is a grammatical process in which words are changed to express different grammatical categories such as tense, case, and gender. In English, inflection is most commonly seen with verbs, where the ending of the verb changes to reflect the tense (e.g. "sing" becomes "sang" to indicate the past tense), but it can also occur with nouns, pronouns, and other parts of speech. Inflection is a fundamental aspect of many languages, and is an important concept in natural language processing (NLP), where it is used to help algorithms understand and generate grammatically correct sentences.
By ChatGPT

By Source:

Inflection
: “…is a process of word formation, in which a word is modifi ed to express different grammatical categories such as tense, case, voice, aspect, person, number, gender…”	(https://en.wikipedia.org/wiki/Inflection)

## What is the difference between inflection and derived words?
Inflection and derived words are two related but distinct concepts in linguistics. Inflection refers to the process of changing the form of a word to express different grammatical categories such as tense, case, and gender. For example, in English, the verb "sing" changes to "sang" to indicate the past tense. In contrast, derived words are words that are created by adding affixes (prefixes or suffixes) to existing words. For example, the word "unhappy" is derived from the word "happy" by adding the prefix "un-". Both inflection and derived words are important for natural language processing (NLP) algorithms, as they help to provide additional context and meaning to words and sentences. However, they are different processes and serve different purposes in language.
By ChatGPT

By Source:
Inflected vs. derived words
Inflected words: “eat”, “eats”, “eating” => eat Derived words: “democracy” = > “democratize”

## What is the distinction between words?

The distinction between words is a fundamental concept in linguistics, and refers to the way that the meaning of a sentence is conveyed through the use of individual words and the relationships between them. In natural language processing (NLP), the distinction between words is important for several reasons. First, it allows NLP algorithms to understand the structure and meaning of a sentence by identifying the individual words and the relationships between them. Second, it enables algorithms to identify and extract important information from a text, such as named entities, relationships, and sentiment. Finally, it allows algorithms to generate grammatically correct sentences by properly arranging and inflecting the words. Overall, the distinction between words is crucial for NLP algorithms to accurately understand and generate natural language.
By ChatGPT

By Source:

- Capitalization may or may not matter in an application
E.g., bush vs. Bush
- Inflections of a word are typically treated as 1 word, e.g., cat vs. cats
- A lemma is a set of lexical forms with the same stem, major part of speech, and word sense, e.g., cat is the lemma for cat and cats
- A word form is the full inflected or derived form of the word, e.g., cats

## What is the difference between types and tokens?

In natural language processing (NLP), the terms "types" and "tokens" refer to the distinct units of language that are used to construct sentences. A type is a unique word or combination of words, regardless of how many times it appears in a text. For example, the word "the" is a type that appears many times in a text, but it is still considered a single type. A token, on the other hand, refers to each individual instance of a word or combination of words in a text. For example, if the word "the" appears 10 times in a text, it would be represented as 10 tokens. The distinction between types and tokens is important for NLP algorithms, as it allows them to accurately count and analyze the words in a text.

By source:

- The different words in a document corpus are called “Types” of words
The set of unique types forms the vocabulary associated with the corpus E.g., “The cats and the dogs” contains 4 types
- The total number of words in the corpus is the number of tokens
E.g., “The cats and the dogs” contains 5 tokens


## What is LANGUAGE VARIABILITY?
Language variability refers to the fact that natural language can vary widely across different regions, dialects, and speakers. This can make it difficult for natural language processing (NLP) algorithms to accurately understand and generate language, as they must be able to handle a wide range of variations in order to be effective. Some common sources of language variability include regional variations in vocabulary and pronunciation, differences in dialects and accents, and individual differences in the way that people use language. To address language variability, NLP algorithms often use techniques such as stemming, lemmatization, and part-of-speech tagging to normalize the input and output, and may be trained on large amounts of diverse data to improve their ability to handle a wide range of variations.
By ChatGPT

By Source:

- Different forms of a language based on location or social group
    * Dialects
    * African American English (AAE), African American Vernacular English (AAVE)
- Differences between spoken and written language
- Code switching - mixing words from multiple languages even in 1 sentence!

# How to identify similarity between words?

There are various techniques and algorithms that can be used to identify similarity between words in natural language processing (NLP) applications. Some of the main techniques include:

Cosine similarity: Cosine similarity is a measure of the similarity between two words, based on their vectors in a high-dimensional space. The vectors are typically derived from a large corpus of text, and are used to represent the words in a numerical form that can be compared using the cosine similarity formula. This technique can be effective for identifying words that are semantically similar, but may not be effective for identifying syntactically similar words.

Word embeddings: Word embeddings are numerical representations of words that are learned from a large corpus of text using a machine learning algorithm. The embeddings capture the context and meaning of the words, and can be used to identify words that are similar in meaning. This technique can be effective for identifying both semantically and syntactically similar words, but may require a large amount of training data and computational resources.

Edit distance: Edit distance is a measure of the similarity between two words, based on the number of edits (insertions, deletions, or substitutions) that are required to transform one word into the other. This technique can be effective for identifying words that are similar in spelling, but may not be effective for identifying words that are similar in meaning.

Overall, the choice of technique for identifying similarity between words in NLP applications can depend on the specific needs and goals of the task, and may require a combination of different techniques in order to achieve the best results.

By source:

- Edit Distance is a way of quantifying the similarity of two strings
    * Used for auto-correct - figuring out what to autocorrect a misspelled word to
    * And for coreference, e.g., figuring out that “San Jose State President” and “ San Jose State University President” refer to the same entity
- Minimum Edit Distance (MED) is the minimum number of operations (e.g., insertion, deletion, substitution) to convert one string to another
- Levenshtein Distance (LD) is a MED algorithm where each operation has the same weight : each has a costs of 1
E.g., intention and execution has a LD of 5
