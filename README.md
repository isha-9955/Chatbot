# Chatbot
# 💬 Simple Chatbot with TF-IDF and NLTK

A Python-based terminal program that acts as a conversational chatbot. It leverages Natural Language Processing (NLP) techniques to understand user queries and provide relevant responses from a given text corpus, augmented with predefined question-answer pairs.

---

## 🎯 Purpose

To create an interactive chatbot that can:
* Engage in basic greetings. 👋
* Answer questions by finding the most similar information in a provided text. 📚
* Provide direct answers to common, specific queries (like math facts or general knowledge). 🧠

---

## 🧠 Key Features

✅ **Greeting Recognition:** Responds to common salutations like "hello" or "hi". 👋

✅ **Contextual Responses:** Generates answers by identifying the most semantically similar sentence from `Act1Scene1.txt` using TF-IDF and Cosine Similarity. 💬

✅ **Predefined Q&A:** Offers precise answers to a set of hardcoded questions, covering basic math operations and general knowledge. 💡

✅ **Simple Exit Mechanism:** Allows users to end the conversation gracefully by typing "bye" or "thanks". 🚪

✅ **Error Handling:** Provides a default "I don't understand" message when no relevant response is found. ⚠️

---

## 🛠️ Technologies Used

* **Python 3** 🐍 — Core programming language.
* **NLTK (Natural Language Toolkit)** 📖 — For text preprocessing, including sentence tokenization, word tokenization, and lemmatization.
* **scikit-learn** 📊 — Specifically for `TfidfVectorizer` (to convert text into numerical features) and `cosine_similarity` (to measure text similarity).
* **`random`** — For selecting random greeting responses.
* **`string`** — For punctuation handling.
* **`warnings`** — To filter out non-critical warning messages.

---

## 📂 Project Structure

| File                  | Description                                                                                             |
| :-------------------- | :------------------------------------------------------------------------------------------------------ |
| `main.py` (or `chatbot.py`) | The main Python script containing the chatbot's logic.                                                  |
| `Act1Scene1.txt`      | The text corpus (knowledge base) from which the chatbot derives contextual responses. (User-provided) 📚 |

---

## ▶️ How to Run (Google Colab Recommended)

This project is best run in a Google Colab environment due to its ease of setup for Python and NLTK.

1.  **Open Google Colab:** Navigate to <https://colab.research.google.com/> and create a new notebook. 📝

2.  **Upload Text Corpus:**
    * On the left sidebar, click the **folder icon** (Files). 📁
    * Click the **"Upload to session storage" icon** (an upward arrow). ⬆️
    * Upload your `Act1Scene1.txt` file to the root directory of the Colab session.

3.  **Paste the Code:**
    * Copy the entire Python code for the chatbot. 📋
    * Paste it into a code cell in your Colab notebook. 💻

4.  **Run the Code Cell:**
    * Click the **"Play" button** (triangle icon) next to the code cell, or press `Shift + Enter`. ▶️

    **Important Notes for First Run:**
    * The script will first download necessary NLTK data (`punkt`, `wordnet`, `omw-1.4`, `stopwords`). **Ensure these downloads complete successfully.** ✅ Watch the cell output for messages like `[nltk_data] Done downloading package punkt.`
    * If you encounter a `LookupError` (e.g., `punkt_tab not found`), **restart the Colab runtime** (`Runtime` > `Restart session`) and then re-run the cell. This often resolves download issues. 🔄
    * The code assumes your text file is named `Act1Scene1.txt` and is in the same directory as your script. If not, adjust the `f = open("Act1Scene1.txt", ...)` line. ✍️

---

## 💡 How It Works

The chatbot operates on a few core principles:

1.  **Preprocessing:** The input text corpus (`Act1Scene1.txt`) is tokenized into sentences and words, then lowercased, and punctuation is removed. Words are lemmatized (reduced to their base form) to ensure consistent matching.
2.  **Predefined Q&A:** For common queries (like "what is 5 + 3?"), the chatbot first checks a dictionary of predefined questions and provides an exact answer if a match is found. This ensures accuracy for frequently asked, factual questions.
3.  **TF-IDF Vectorization:** If no predefined answer is found, the chatbot converts both the user's query and the sentences from the text corpus into numerical vectors using **Term Frequency-Inverse Document Frequency (TF-IDF)**. TF-IDF assigns weights to words based on how frequently they appear in a document relative to how frequently they appear across all documents, highlighting important terms.
4.  **Cosine Similarity:** The chatbot then calculates the **cosine similarity** between the user's query vector and every sentence vector in the corpus. Cosine similarity measures the cosine of the angle between two vectors, indicating how similar they are in direction (and thus, in meaning).
5.  **Response Generation:** The sentence from the corpus with the highest cosine similarity to the user's query is chosen as the chatbot's response. If the similarity is very low (e.g., zero), it indicates the chatbot doesn't understand the query.

---

## 🔮 Future Enhancements

* **More Sophisticated Preprocessing:** Implement more advanced text cleaning (e.g., handling contractions, slang).
* **Named Entity Recognition (NER):** Identify and extract key entities (people, places, organizations) from text for richer responses.
* **Sentiment Analysis:** Understand the emotional tone of user queries.
* **Dialogue Management:** Maintain context across multiple turns in a conversation.
* **Integration with External APIs:** Connect to external services (e.g., weather APIs, Wikipedia) for dynamic information retrieval.
* **Machine Learning Models:** Explore more advanced NLP models like word embeddings (Word2Vec, GloVe) or transformer-based models (BERT, GPT) for more nuanced understanding and generation.
* **User Interface:** Develop a simple graphical user interface (GUI) instead of a terminal-based one.

---

## 🤝 Contributing

Contributions are welcome! If you have suggestions for improvements or new features, please:

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/YourFeature`).
3.  Make your changes.
4.  Commit your changes (`git commit -m 'Add new feature'`).
5.  Push to the branch (`git push origin feature/YourFeature`).
6.  Create a new Pull Request.

---

## 👩‍💻 Developed By

**Isha Zope**  
🔗 GitHub: https://github.com/isha-9955
