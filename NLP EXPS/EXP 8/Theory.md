# Named Entity Recognition (NER)

## Aim

To implement a Named Entity Recognizer (NER) using Python and SpaCy library to identify and classify named entities such as persons, organizations, locations, dates, and monetary values from a given text input.

---

## Theory

Named Entity Recognition (NER) is a subtask of Natural Language Processing (NLP) that seeks to locate and classify named entities mentioned in unstructured text into predefined categories such as:

- **Person Names** (e.g., Tim Cook)
- **Organizations** (e.g., Apple Inc.)
- **Geopolitical Entities (GPE)** such as countries, cities (e.g., Seattle, Germany)
- **Dates** (e.g., 2024)
- **Monetary Values** (e.g., $5 billion)

NER helps in extracting structured information from unstructured text data, making it easier to analyze and utilize in various applications like information retrieval, question answering, and automated summarization.

SpaCy is a powerful open-source NLP library in Python that provides pre-trained models to perform NER efficiently. It uses deep learning models trained on large corpora to recognize entities with high accuracy. The `en_core_web_sm` model is a lightweight English model sufficient for basic NER tasks.

The `displacy` visualizer allows users to see entities highlighted with different colors for easy interpretation.

# Named Entity Recognition (NER)

Named Entity Recognition (NER) is a fundamental task in Natural Language Processing (NLP) that focuses on identifying and categorizing key pieces of information, called entities, within unstructured text. These entities typically include names of people (PERSON), organizations (ORG), locations (GPE), dates (DATE), monetary values (MONEY), and other domain-specific terms. 

NER plays a crucial role in converting raw text data into structured information, which is essential for a wide range of applications such as information retrieval, machine translation, question answering systems, text summarization, and more. By automatically extracting meaningful entities from large volumes of text, NER helps machines understand and analyze human language more effectively.

Modern NER systems, like those implemented in the SpaCy library, use advanced machine learning and deep learning techniques. These systems are trained on large annotated corpora, enabling them to recognize entities with high accuracy even in complex or ambiguous contexts. SpaCy provides pre-trained models that support multiple entity types and allow users to quickly deploy NER in their projects with minimal setup.

Additionally, visualization tools such as SpaCy's `displacy` enable users to see detected entities highlighted in different colors, making it easier to interpret and verify the results.

Overall, NER is a powerful NLP technique that significantly enhances the ability to process and extract actionable insights from textual data across various industries and research domains.


---

## Conclusion

In this project, a Named Entity Recognizer was implemented using the SpaCy library in Python. The NER model successfully identified and classified multiple types of entities such as persons, organizations, locations, dates, and monetary values from a sample text input.

The use of SpaCy simplifies the process of applying complex NLP models and provides visual tools for better understanding. This approach can be applied in various domains requiring automated information extraction from text.

Overall, SpaCy's NER provides an effective and efficient solution for extracting meaningful entities from raw text, aiding in better data analysis and decision-making.

---
