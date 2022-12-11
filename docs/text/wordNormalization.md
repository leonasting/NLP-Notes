# Word Normalization
Word normalization is the process of converting a word to a standardized or canonical form in order to make it easier for natural language processing (NLP) algorithms to work with. This typically involves a combination of techniques such as stemming, lemmatization, and part-of-speech tagging, which are used to reduce the word to its core components and remove variations that do not affect its meaning. The goal of word normalization is to make the word more consistent, uniform, and predictable, which can improve the accuracy and efficiency of NLP algorithms. Word normalization is an essential step in many NLP tasks, such as text classification, summarization, and translation, and can help to improve the performance of NLP systems by reducing the complexity and variability of the input
-By ChatGPT


## Waht is Case Folding and mention its pittfalls?
Case folding: This involves converting all letters in the text to either upper or lower case, in order to make the text more uniform and easier to process.

Although case folding is a simple and effective technique for text normalization, it does have some potential pitfalls and limitations that users and developers should be aware of. Some of the main pitfalls of case folding include:

Loss of information: Case folding can reduce the amount of information in a text, as it removes the case information from the letters. This can make it more difficult for NLP algorithms to accurately understand the meaning and intent of the text, and may reduce the overall quality of the results.

Inability to handle certain languages: Case folding is not effective for all languages, as some languages use case to convey important information. For example, in German, the case of a noun can indicate its gender and case, and in Turkish, the case of a word can change its meaning. In these languages, case folding can lead to inaccurate or misleading results.

Unintended changes: Case folding can sometimes lead to unintended changes in the text, such as changing the spelling of a word or removing important punctuation marks. For example, the word "iPad" would be converted to "ipad" by case folding, which could change the meaning of the word or cause it to be misinterpreted by an NLP algorithm.

Overall, it is important to be aware of these potential pitfalls when using case folding for text normalization, and to carefully consider whether it is appropriate for a given language and NLP task.

By Source:

- Mapping all letters to lower case
- Reduces that vocabulary size since all capitalizations of the word are represented with 1 token, e.g., “Cats” & “cats”
- Undesirable for some applications, e.g., sentiment analysis

## What is Stemming, what are is advantages and pitfalls?

Stemming is a technique that is commonly used in natural language processing (NLP) to reduce words to their core stems, typically by removing suffixes and other word endings. The goal of stemming is to normalize related words and improve the accuracy of NLP algorithms, by reducing the complexity and variability of the input. Some of the main advantages of stemming include:

Simplicity: Stemming is a simple and straightforward technique that is easy to understand and implement. It requires minimal setup and can be applied to any piece of text with minimal effort.

Effectiveness: Stemming can be an effective way to reduce the complexity and variability of a text, making it easier for NLP algorithms to accurately understand and generate language.

Efficiency: Stemming can improve the efficiency of NLP algorithms by reducing the amount of data that needs to be processed. This can help to make NLP systems faster and more scalable, and can reduce the computational resources that are required to perform NLP tasks.

However, there are also some potential pitfalls and limitations of stemming that users and developers should be aware of, including:

Loss of information: Stemming can remove important information from a word, such as its suffixes and endings, which can make it more difficult for NLP algorithms to accurately understand the meaning and context of the word.

Inability to handle certain languages: Stemming is not effective for all languages, as some languages use suffixes and endings to convey important information. In these languages, stemming can lead to inaccurate or misleading results.

Unintended changes: Stemming can sometimes lead to unintended changes in the word, such as changing its spelling or removing important letters. This can cause confusion and misinterpretation by NLP algorithms.

Overall, the advantages and pitfalls of stemming should be carefully considered when deciding whether to use.

By Source:

- Stemming converts infl ected words to the same word stem or root (though not necessarily the morphological root of the word)
- The Porter Stemmer is a popular algorithm (implemented in nltk as well)
    * Stems “apple” to “appl”, “eating” to “eat”
    * Stems "universal", "university", and "universe" to “univers" (overstemming)
    * Stems: ”alumnus" → "alumnu", "alumni" → "alumni", "alumna"/"alumnae" → “alumna" (understemming)
- Challenges of stemming
  * Overstemming and understemming
  * The text is changed in a way that makes it hard to read because the stemmed words are not real words but truncated words/crudely shortened words (you may need to review the text as part of the modeling process)
## What is Lemmatization, what are is advantages and pitfalls?
  Lemmatization is a technique that is commonly used in natural language processing (NLP) to reduce words to their base forms, called lemmas. The goal of lemmatization is to normalize related words and improve the accuracy of NLP algorithms, by reducing the complexity and variability of the input. Some of the main advantages of lemmatization include:

Precision: Lemmatization is a more precise technique than stemming, as it uses the full context of a word to determine its lemma. This can improve the accuracy of NLP algorithms and reduce the risk of misinterpretation or confusion.

Robustness: Lemmatization is a more robust technique than stemming, as it can handle a wider range of languages and variations. This can make it more effective for NLP tasks that involve multiple languages or complex text.

Flexibility: Lemmatization is a flexible technique, as it allows users and developers to specify the part-of-speech of a word in order to determine its lemma. This can be useful for handling words that have multiple meanings or uses.

However, there are also some potential pitfalls and limitations of lemmatization that users and developers should be aware of, including:

Complexity: Lemmatization is a more complex technique than stemming, as it requires more computational resources and may be more difficult to implement and use.

Lack of standardization: Lemmatization can be affected by the choice of lemma database or lexicon, which can vary depending on the language, domain, and application. This can make it more difficult to compare the results of different lemmatization algorithms.

Limited coverage: Lemmatization may not be effective for all words, as some words may not have a clear lemma or may not be included in the lemma database. This can lead to incomplete or inaccurate results.

Overall, the advantages and pitfalls of lemmatization should be carefully considered when deciding whether to use this technique for text normalization in NLP applications.

By Source:

- Lemmatization is a more sophisticated approach than stemming — it returns the base or dictionary form of a word, which is known as the lemma
- The lemmas are extracted from a lexical knowledgebase like WordNet (https:// wordnet.princeton.edu) — implemented in python as well: nltk.WordNetLemmatizer()
- The resulting text is readable unlike in stemming

- Shortcomings
    * Usually lemmatization requires you to specify the part of speech of a word (otherwise assumes it’s a noun and if it cannot find it in its noun database would not change/lemmatize it)
    * Lemmatization cannot handle unknown words, e.g., the Porter stemmer would stem both iPhone and IPhones to iphon, while a WordNet lemmatized would leave both of them unchanged
    * Languages with more complex morphology benefit more from stemming & lemmatization


## Recall vs Prexision of Stemming vs Lemmatization

Recall is a measure of how many relevant items are retrieved by an NLP algorithm, and is calculated as the number of relevant items retrieved divided by the total number of relevant items. **Stemming typically has a higher recall than lemmatization, as it is a more aggressive technique that can reduce a wider range of words to their stems**. This can make it more effective at capturing the full range of relevant information in a text, but can also increase the risk of false positives and other errors.

Precision is a measure of how many retrieved items are relevant, and is calculated as the number of relevant items retrieved divided by the total number of items retrieved.**Lemmatization typically has a higher precision than stemming, as it is a more precise technique that uses the full context of a word to determine its lemma**. This can reduce the risk of false positives and other errors, but can also reduce the recall of the algorithm by excluding some relevant words from the output.

By Source:

- Lemmatization has better precision but lower recall than stemming
- Recall refers to how well the algorithm is at discovering all words that can be mapped to the same “root”
- Precision refers to how well the algorithm preserves the meaning of the words that it changes (e.g., if stemming to “univers” loses the differentiation between “university” and “universe”)
- Both lemmatization and stemming increase recall and reduce precision relative to the original text

## Recall vs Prexision of Stemming vs Lemmatization
