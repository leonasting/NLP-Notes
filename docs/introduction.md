# Introduction to Natural Language Processing

## What is Natural Language Processing(NLP)

Natural language processing (NLP) is a subfield of linguistics, computer science, and artificial intelligence concerned with the interactions between computers and human (natural) languages. It focuses on making it possible for computers to read, understand, and generate human language, including speech and text. This is a challenging task because human language is complex and can be difficult for computers to process. Some common applications of NLP include language translation, sentiment analysis, and automatic summarization.
By: Chat GPT


## Explain the NLP Usecases

### Information Retrieval IR

Information retrieval (IR) is the process of finding and retrieving information from a collection of documents or other sources. This typically involves using keywords or other search terms to find relevant documents, and then ranking the results based on their relevance to the search query. Information retrieval systems can be used for a wide range of applications, including online search engines, digital libraries, and personal databases. The goal of IR is to provide users with quick and accurate access to the information they need, and to help them find relevant information more easily.
By: Chat GPT

The primary task of finding the document **d** from the **D** documents in some collection that best matches a query **q**
Often, a list of documents is retrieved instead of just one.Often, a list of documents is retrieved instead of just one.

### Text summarization

Text summarization is the process of automatically generating a shorter version of a longer text document while retaining its most important information. This can be useful for a variety of applications, including reducing the amount of text that needs to be read, condensing a document for easier reference, or creating a summary for a search engine. There are two main types of text summarization: extractive summarization, which selects important sentences from the original text, and abstractive summarization, which uses natural language processing to generate a summary that is not necessarily based on the original text.
By: Chat GPT

### Quesiton Answering
Question answering (QA) is a common use case for natural language processing (NLP). In a QA system, the user poses a question in natural language, and the system attempts to generate an accurate and relevant answer. This can be useful in a variety of applications, such as providing answers to common customer service questions, helping users find information on a website, or providing answers to questions in a digital assistant or chatbot. To build a QA system, NLP techniques are used to process and understand the user's question, search for relevant information, and generate a natural language response.

By: Chat GPT

Ideally more “semantically based” and focused (e.g., one answer) than pure IR.<br>
Factoid question-answering typically uses:

- IR to retrieve relevant text passages from document(s)
- Reading comprehension algorithm to answer the question

## Why Natural language processing is hard ?
Natural language processing (NLP) is a difficult task because human language is complex and can be difficult for computers to process. Some of the challenges of NLP include:

- Ambiguity: Natural language is often ambiguous, with the same words having multiple meanings depending on the context. This can make it difficult for computers to determine the correct interpretation of a sentence.

- Vagueness: Natural language is often vague, with words and phrases that are imprecise or incomplete. This can make it difficult for computers to determine the intended meaning of a sentence.

- Imperfect input: Human language is not always spoken or written perfectly, and NLP systems must be able to handle incomplete, incorrect, or inconsistent input.

- Lack of standardization: Natural language varies widely across different regions, dialects, and languages, making it difficult to develop NLP systems that can handle all variations accurately.

- Computational complexity: NLP algorithms can be computationally intensive, requiring significant processing power and memory to handle large amounts of data.

- Lack of labeled data: Many NLP tasks require large amounts of labeled training data to learn from, but this data can be difficult and time-consuming to collect and annotate.

- Domain specificity: NLP systems often have to be tailored to specific domains or tasks, which can require a significant amount of time and effort to develop and maintain.

- Natural language variation: Natural language varies widely across different regions, dialects, and languages, making it difficult to develop NLP systems that can handle all variations accurately.

- Cultural and social factors: Natural language is influenced by cultural and social factors, such as the speaker's background, gender, and age, which can make it difficult for NLP systems to interpret and generate language accurately.
Overall, the complexity of natural language and the various challenges it presents make NLP a difficult task.
By GPT.

By other sources:

- Homonymy - a word has completely different “word senses” (or meanings).<br>
**eg** A bank can be a financial institution, the physical building of a financial institution, or the edge of a river (river bank)

- Lexical ambiguity - a word can have different roles in a sentence (noun, verb, adjective)<br>
**eg** “He saw her duck” - downwards move or waterfowl?

- Coreference resolution is challenging (due to Pronoun)
**eg** “Eduardo told me that Miguel was very sick so I took him to the hospital”

## Explain pittfalls of  Natural language processing ?

There are several potential pitfalls and limitations to natural language processing (NLP) that users and developers should be aware of. Some of the main pitfalls of NLP include:

- Biased algorithms: NLP algorithms can be trained on biased or unrepresentative data, leading to biased or unfair outputs. For example, an NLP system trained on biased data could generate biased language or make biased decisions.

- Lack of context: NLP algorithms often struggle to understand the context of a given text, which can lead to inaccurate or misleading results. For example, an NLP system might not be able to determine the tone or intent of a text, or might not understand the implications of certain words or phrases.

- Misunderstandings: NLP algorithms can sometimes misunderstand or misinterpret text, leading to incorrect or nonsensical outputs. For example, an NLP system might generate an answer to a question that does not actually address the question, or might generate language that is grammatically incorrect or nonsensical.

- Limited capabilities: NLP algorithms are not perfect and have limitations in terms of the tasks they can perform and the language they can handle. For example, an NLP system might not be able to handle complex or unusual sentences, or might not be able to handle multiple languages or dialects.

Overall, it is important to be aware of these potential pitfalls when using or developing NLP systems, and to take steps to address them in order to improve the accuracy and fairness of the results.

By other sources:-

- ETHICS QUESTIONS:
    * Powerful surveillance, privacy violations
    *  Profiling & Bias, e.g., in recruiting  and Impact on jobs
    * Use of AI to more effectively manipulate humans — impact on human agency

- EXPLAINABILITY:
    * Popular algorithms are black boxes — not possible to find out how and why a recommendation or decision is made by an AI system
    * Often NLP algorithms are trained on very large datasets that cannot be moderated in detail — how do we know the algorithm has not learned something biased, wrong, and possibly dangerous
    *  How can we audit an NLP application before deployment to ensure it always behaves correctly, safely, etc.?
- SUSTAINABILITY:
    * Carbon footprint of AI is significant https://arxiv.org/abs/1906.02243
    * A single training session of GPT-3 is equivalent to driving to the moon and back (and costs ~$4.6 million on low cost cloud infrastructure)  https://www.theregister.com/2020/11/04/gpt3_carbon_footprint_estimate/
    * Advancements in Deep Learning have been due to increased model sizes and larger training datasets
- Cyber Security:
    * AI can improve cyberattack detection BUT it can also amplify the effectiveness of cyberattacks
    * Social engineering attacks can become much more powerful through personalization
    *  Intrusion into trusted Intelligent “Personal Assistants” can cause a lot of damage
