# -MENUMANAGER-Menu-Q-A-Assistant# 🍽️ Menu Q&A Assistant using Semantic Search and Transformers

An AI-powered Menu Question Answering Assistant that allows users to ask natural language questions about a restaurant menu and receive relevant dish recommendations along with direct answers.

Built as part of the **MenuManager Intern Project – Track B: Menu Q&A Assistant**. :contentReference[oaicite:0]{index=0}

---

## 📌 Project Overview

Traditional menu search relies on exact keywords and struggles with natural language queries such as:

- "Suggest a healthy meal"
- "What vegan dishes do you have?"
- "Cheap dessert options"
- "Is butter chicken spicy?"

This project uses **Transformer models** and **Semantic Search** to understand the meaning of user queries and retrieve the most relevant menu items.

---

## 🚀 Features

✅ Semantic Search using Sentence Embeddings

✅ Natural Language Question Answering

✅ Top-K Relevant Dish Retrieval

✅ Similarity Score Ranking

✅ Interactive Command Line Interface (CLI)

✅ Support for basic filters like:
- Vegan dishes
- Price constraints (e.g., under ₹200)

---

## 🛠️ Technologies Used

- Python
- Google Colab
- Pandas
- NumPy
- Scikit-Learn
- Hugging Face Transformers
- Sentence Transformers

---

## 🤖 Models Used

### 1. Sentence Embedding Model

**Model:** `sentence-transformers/all-MiniLM-L6-v2`

Purpose:
- Converts menu items into embeddings (vectors).
- Converts user queries into embeddings.
- Enables semantic similarity search.

---

### 2. Extractive Question Answering Model

**Model:** `distilbert-base-cased-distilled-squad`

Purpose:
- Extracts direct answers from the retrieved menu context.

---

## 📂 Dataset

Dataset: `menu.csv`

Columns:

| Column | Description |
|---------|-------------|
| dish_name | Name of the dish |
| category | Starter, Main Course, Dessert, Beverage, etc. |
| price | Price of the dish |
| description | Short description of the dish |
| dietary_tags | Veg, Non-Veg, Vegan, Gluten-Free, Spicy, etc. |

---

## 🏗️ Project Architecture

```text
User Question
      ↓
Sentence Transformer
      ↓
Query Embedding
      ↓
Cosine Similarity Search
      ↓
Top Matching Dishes
      ↓
Question Answering Model
      ↓
Direct Answer
```

---

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/Menu-QA-Assistant.git
cd Menu-QA-Assistant
```

Install dependencies:

```bash
pip install transformers sentence-transformers torch pandas numpy scikit-learn
```

---

## ▶️ Running the Project

Run the notebook in Google Colab or Jupyter Notebook.

Or run the CLI version:

```bash
python app.py
```

---

## 💬 Example Queries

```text
What vegan dishes do you have?
Suggest a healthy meal.
Cheap dessert options.
Paneer dishes.
Is butter chicken spicy?
Recommend a beverage.
Gluten free food.
Starter under 200.
```

---

## 📸 Example Output

```text
Question:
What vegan dishes do you have?

Top Matches:
1. Vegan Salad
2. Grilled Vegetables
3. Fruit Bowl

Direct Answer:
Vegan Salad
```

---

## 📊 How It Works

### Step 1
Load `menu.csv`.

### Step 2
Create a combined text field:

```text
dish_name + category + price + description + dietary_tags
```

### Step 3
Generate embeddings using:

```python
SentenceTransformer("all-MiniLM-L6-v2")
```

### Step 4
Generate an embedding for the user's query.

### Step 5
Compute cosine similarity.

### Step 6
Retrieve the top matching dishes.

### Step 7
Pass the best match into:

```python
pipeline("question-answering")
```

### Step 8
Display the answer and ranked results.

---

## 📈 Future Improvements

- Web Interface using Streamlit or Flask
- Voice-based Menu Assistant
- Better filtering and recommendation system
- Larger LLM integration
- Personalized recommendations

---

## ⚠️ Limitations

- Semantic search struggles with numeric reasoning (e.g., exact price filtering).
- Extractive QA sometimes returns phrases instead of Yes/No answers.
- Performance depends on the quality of menu descriptions.

---

## 📚 Learning Outcomes

Through this project, I learned:

- Transformer-based NLP pipelines
- Sentence embeddings
- Semantic search
- Extractive question answering
- Hugging Face ecosystem
- Building end-to-end NLP applications

---

## 👨‍💻 Author

**LokeshWaran R P**

BE Computer science

MenuManager Internship Project – Track B

---

## ⭐ Acknowledgements

- Hugging Face
- Sentence Transformers
- MenuManager Internship Program
- Google Colab
