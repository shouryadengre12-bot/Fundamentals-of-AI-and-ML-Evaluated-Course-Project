# Smart Lecture Summarizer & Flashcard Generator

## About The Project
I built this AI-powered tool to help students study large amounts of text. Instead of manually reading through long lecture transcripts, this script takes those notes and generates a short summary. From that summary, it uses Natural Language Processing (NLP) to automatically create fill-in-the-blank flashcards for key dates, concepts, and entities.

I created this as a capstone for my AI/ML course to apply what I learned about Transformer models and NLP in a practical way.

### Core Features
* **Summarization:** Uses the `facebook/bart-large-cnn` model from Hugging Face to summarize long text.
* **Automated Flashcards:** Uses `spaCy` (Named Entity Recognition) to find testable facts and turn them into study questions.
* **Dynamic Sizing:** The script automatically changes the summary length depending on how much text you paste in.

---

## Prerequisites
Before you begin, ensure you have **Python 3.8 or higher** installed on your system. 

---

## Installation & Setup
Follow these steps to get the project running on your local machine.

**1. Clone the repository**
```bash
git clone https://github.com/shouryadengre12-bot/Fundamentals-of-AI-and-ML-Evaluated-Course-Project.git
cd Fundamentals-of-AI-and-ML-Evaluated-Course-Project
```

**2. Create a Virtual Environment (Recommended)**
It is highly recommended to run this in a virtual environment to avoid dependency conflicts.

*Windows:*
```bash
python -m venv venv
venv\Scripts\activate
```

*macOS/Linux:*
```bash
python3 -m venv venv
source venv/bin/activate
```

**3. Install Dependencies**
Install the required Python libraries. Note that this project requires `transformers` version 4.x for pipeline stability.
```bash
pip install "transformers<5" torch spacy
```

**4. Download the spaCy Language Model**
The flashcard generator requires the English core web model to function.
```bash
python -m spacy download en_core_web_sm
```

---

## How to Use
1. Open the `main.py` file in your preferred text editor.
2. Locate the `sample_lecture` variable at the bottom of the script.
3. Paste your own lecture notes or text into this variable.
4. Run the script from your terminal:
```bash
python main.py
```
*(Note: The very first time you run the script, it will take a minute or two to download the BART AI model to your machine. Subsequent runs will be much faster).*

---

## Example Output
When you run the script, the console will output the generated summary and flashcards:

```text
Loading AI models... (This might take a minute on the first run)
Models loaded successfully!

Generating summary...

--- LECTURE SUMMARY ---
Machine learning is a subfield of artificial intelligence. In 1959, Arthur Samuel coined the term machine learning, defining it as a field of study that gives computers the ability to learn without being explicitly programmed. Today, neural networks are heavily used in modern machine learning tasks like image recognition.

Generating flashcards...

--- STUDY FLASHCARDS ---
Card 1:
Q: ________ is a subfield of artificial intelligence.
A: Machine learning

Card 2:
Q: In ________, Arthur Samuel coined the term machine learning...
A: 1959
```

---

## Project Structure
* `main.py` — The core application containing the `LectureAssistant` class.
* `requirements.txt` — List of required Python packages for the environment.
* `README.md` — Project documentation and setup guide.
