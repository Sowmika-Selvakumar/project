# 🤖 TDS Virtual TA

A Retrieval-Augmented Generation (RAG) based FastAPI system to automatically answer student queries using IIT Madras' **Tools in Data Science** course content and Discourse forum posts.

## Deployed link
[https://tds-virtual-ta-fin.onrender.com/docs]

## 📂 Project Structure

project/
├── api/
│   └── index.py               # API routes and logic
├── scraping/
│   ├── scrape\_course.py       # Scrapes course markdown content
│   └── scrape\_discourse.py    # Scrapes IITM Discourse threads
├── markdown\_files/            # Local storage of markdown content
├── downloaded\_threads/        # Local storage of forum threads
├── app.py                     # FastAPI entrypoint
├── preprocess.py              # Prepares and populates the knowledge base
├── requirements.txt           # Python dependencies
├── .gitignore
├── test.py                    # Test script 
├── knowledge\_base.db          # SQLite DB of vectorized content
└── vercel.json                # Vercel deployment config 


## ⚙️ Features

- 🔍 Semantic search over course and forum content
- 🧠 Vector database using text embeddings
- ⚡ FastAPI backend with `/ask` endpoint
- 🕸️ Automated content scraping (markdown + Discourse)
- ☁️ Deployable on Render or Vercel


## 🚀 Getting Started

### 1. Clone the Repo

```bash
git clone https://github.com/Sowmika-Selvakumar/project.git
cd project
````

### 2. Create and Activate Virtual Environment

```bash
python -m venv venv
.\venv\Scripts\activate    # For Windows
# OR
source venv/bin/activate  # For Mac/Linux
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Set API Key

Set your environment variable:

```powershell
$env:API_KEY = "your_openai_or_other_api_key_here"
```

Or use a `.env` file:

```
API_KEY=your_openai_or_other_api_key_here
```


## 🛠️ Run the App

### Build the Knowledge Base

```bash
python preprocess.py
```

### Start the FastAPI Server

```bash
uvicorn app:app --host=127.0.0.1 --port=8000 --reload
```

Visit: [http://127.0.0.1:8000](http://127.0.0.1:8000)
Docs: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)

---

## 📡 Deployment

### 🌐 Deploy on Render

* Connect your GitHub repo to [Render](https://render.com/)
* Set the **start command** as:

```bash
uvicorn app:app --host=0.0.0.0 --port=10000
```

* Add `API_KEY` as an environment variable
* Use `requirements.txt` for dependencies

---

## 🧪 API Usage

### `/ask` Endpoint (POST)

**Request body**:

```json
{
  "query": "How to handle missing data in pandas?"
}
```

**Sample response**:

```json
{
  "answer": "You can use df.fillna() or df.dropna() to handle missing values in pandas.",
  "sources": ["markdown_files/week3.md"]
}
```

---

## 📝 License

This project is licensed under the [MIT License](LICENSE).

---

## 👩‍💻 Author

**Sowmika Selvakumar**
Student, SRMIST Ramapuram & IIT Madras BS DS Program
[GitHub Profile](https://github.com/Sowmika-Selvakumar)

```

---


