# Experiment 5 : Text Preprocessing on Customer Feedback Using NLTK

## Aim
To perform fundamental Natural Language Processing (NLP) text preprocessing steps—including tokenization, punctuation filtering, stopword removal, and lemmatization—on customer feedback text using Python's `nltk` library.

## Algorithm

1. **Start** the program.
2. **Import Libraries**: Import `nltk` along with `word_tokenize` (from `nltk.tokenize`), `stopwords` (from `nltk.corpus`), and `WordNetLemmatizer` (from `nltk.stem`).
3. **Download NLTK Resources**: Download the required tokenizer models and lexical corpora (`punkt`, `punkt_tab`, `stopwords`, and `wordnet`) using `nltk.download()`.
4. **Define Input Text**: Store the sample customer feedback paragraph in a string variable `text` and display the original text.
5. **Tokenize Text**: Split `text` into individual word and punctuation tokens using `word_tokenize(text)`.
6. **Filter Punctuation & Remove Stopwords**:
   * Load the English stopword set via `set(stopwords.words('english'))`.
   * Retain only alphabetic tokens (`word.isalpha()`) whose lowercase forms are not present in `stop_words`.
7. **Lemmatize Tokens**:
   * Initialize `WordNetLemmatizer()`.
   * Convert each filtered token to lowercase and reduce it to its base dictionary form using `lemmatizer.lemmatize(word.lower())`.
8. **Display Preprocessed Outputs**: Print the tokenized list, stopword-filtered tokens, and final lemmatized words.
9. **Stop** the program.

## Functions and Methods Used

| Category | Function / Class | Purpose / Description |
| :--- | :--- | :--- |
| **Resource Management** | `nltk.download()` | Downloads required NLTK tokenizers (`punkt`, `punkt_tab`) and corpora (`stopwords`, `wordnet`) |
| **Tokenization** | `word_tokenize()` | Splits raw text into individual word and punctuation tokens |
| **Text Filtering** | `stopwords.words('english')` | Retrieves standard English stopwords for noise reduction |
| | `str.isalpha()` & `str.lower()` | Filters out punctuation/numeric tokens and standardizes text casing |
| **Lemmatization** | `WordNetLemmatizer()` | Initializes the WordNet morphological analyzer |
| | `lemmatizer.lemmatize()` | Converts inflected words into their canonical base dictionary forms |

## Program

import nltk  
from nltk.corpus import stopwords  
from nltk.stem import WordNetLemmatizer  
from nltk.tokenize import word_tokenize  
nltk.download("punkt")  
nltk.download("punkt_tab")  
nltk.download("stopwords")  
nltk.download("wordnet")  
text = """The product quality is excellent and the delivery service was very fast.  
However, the packaging could have been better."""  
print("---- Original Text ----")  
print(text)  
tokens = word_tokenize(text)  
print("\nTokenized Words:")  
print(tokens)  
stop_words = set(stopwords.words("english"))  
filtered_tokens = [  
    word for word in tokens if word.lower() not in stop_words and word.isalpha()  
]  
print("\nAfter Stopword Removal:")  
print(filtered_tokens)  
lemmatizer = WordNetLemmatizer()  
lemmatized_words = [  
    lemmatizer.lemmatize(word.lower()) for word in filtered_tokens  
]  
print("\nAfter Lemmatization:")  
print(lemmatized_words)  


## Output
<img width="1342" height="362" alt="image" src="https://github.com/user-attachments/assets/9a865709-d7ea-4655-83fb-7b520cbbbe70" />


## Result
The program successfully performed tokenization, punctuation filtering, stopword removal, and lemmatization on the customer feedback text using the NLTK library.
