# 📚 LLM Book Recommender System
An intelligent book recommendation system powered by Large Language Models (LLMs), vector search, and emotion detection. Users can input a book preference in natural language, select a desired category and tone, and receive personalized book suggestions with summaries.


## 🚀 Features
🔍 Natural Language Book Search — Search books by entering descriptive text (e.g., "A book about World War II").

🗂️ Category Filter — Choose genres like Fiction, Suspense, Romance, etc.

🎭 Tone Filter — Select tones like Joy, Sadness, Fear, etc. based on emotion analysis of descriptions.

🤖 Zero-Shot Classification — Auto-categorizes books using LLM embeddings and vector search.

💬 Emotion Detection — Uses transformer models to predict the emotional tone of book descriptions.

🖼️ Interactive UI — Built with Gradio for an intuitive user experience.

📘 Description Viewer — Click on any recommended book to read its synopsis.


## 🛠️ Tech Stack
| Tool/Library            | Purpose                                  |
| ----------------------- | ---------------------------------------- |
| **Python**              | Core programming language                |
| **Pandas, NumPy**       | Data cleaning and preprocessing          |
| **Matplotlib, Seaborn** | EDA and visualization (optional)         |
| **Langchain**           | Vector search & zero-shot classification |
| **ChromaDB**            | Embedding storage for semantic search    |
| **Transformers**        | Emotion detection from book descriptions |
| **Gradio**              | Web interface/dashboard                  |
| **KaggleHub**           | Dataset retrieval from Kaggle            |
| **python-dotenv**       | Managing environment variables           |


## 🧠 Project Workflow
#### 1. Data Collection
* Dataset of books retrieved from Kaggle via KaggleHub.

#### 2. Data Cleaning & Preprocessing
* Used Pandas and NumPy to remove nulls, duplicates, and unnecessary columns.

#### 3. Vector Search & Categorization
* Used LangChain components:
    * TextLoader to read book descriptions.
    * CharacterTextSplitter for chunking text.
    * Chroma as the vector store.
* Performed zero-shot classification to label book categories.
  
#### 4. Emotion Detection
* Applied Hugging Face transformer models to detect emotions in book descriptions.
* Stored results in a new dataset (`books_with_categories.csv`).

#### 5. Frontend with Gradio
* Designed an interactive UI with:

    * Input textbox for user query
    * Dropdowns for category and emotional tone
    * Book cards with clickable details

* Displayed top 16 matching books with their titles and detailed description.

## 📂 Project Structure
```bash
llm-book-recommender/
│
├── datasets/
│   └── books.csv                                    # Original dataset
|   └── books_cleaned.csv                            # Cleaned dataset
|   └── books_with_categories.csv                    
|   └── books_with_emotions.csv                     
│
├── notebooks/
│   └── data-exploration.ipynb                        # Basic Cleaning
│   └── vector-search.ipynb                          # Used zero-shot classification
│   └── sentiment-analysis.ipynb                     # Used HF model
│   └── tagged_description.txt                       # Tagged descriptions for vector search
|
├── gradio-dashboard.py                              # Backend & frontend logic
├── requirements.txt                                 # Required packages
├── .env                                             # API keys and environment configs
└── README.md                                        # Project documentation

```


## 🧪 How to Run Locally
#### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/llm-book-recommender.git
cd llm-book-recommender
```

#### 2. Create a Virtual Environment
```bash
python -m venv venv
source venv/bin/activate  # on linux
venv\Scripts\activate     # on Windows
```

#### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

#### 4. Set Environment Variables
```bash
OPENAI_API_KEY= your_api_key
HUGGINGFACE_API_KEY = your_api_key
```

#### 5. Run the App
```bash
python app.py
```

