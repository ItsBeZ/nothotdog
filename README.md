# Not Hot Dog Web App 🍔❌🌭

This is a simple web application built with **Flask** that detects whether an image is a **hot dog** or **not a hot dog** using a **Hugging Face machine learning model**.

It’s inspired by the classic "Hot Dog or Not Hot Dog" app from *Silicon Valley*.

---

## Example JSON Output

```json
[
  {
    "label": "hot dog",
    "score": 0.9457844495773315
  },
  {
    "label": "not hot dog",
    "score": 0.054215509444475174
  }
]
```

---

## Setup Instructions (Windows)

### 1. Clone the repository

```bash
git clone https://github.com/<YourUsername>/nothotdog.git
cd nothotdog
```

### 2. Create a virtual environment

```cmd
python -m venv .venv
.venv\Scripts\activate
```

### 3. Install required packages

```cmd
pip install flask python-dotenv requests
```

### 4. Create a `.env` file

Copy `.env.example` to `.env`:

```cmd
copy .env.example .env
```

Add your Hugging Face API key:

```
HUGGING_FACE_API_URL=https://api-inference.huggingface.co/models/julien-c/hotdog-not-hotdog
HUGGING_FACE_API_KEY=your_hugging_face_api_key_here
```

> **Important:** Do not push `.env` to GitHub. The `.gitignore` already prevents this.

### 5. Run the app

```cmd
python web.py
```

Open your browser at [http://127.0.0.1:5000/](http://127.0.0.1:5000/) and start testing!

---

## File Structure

```
nothotdog/
│
├── web.py              # Flask server code
├── .env.example        # Example environment variables (API key placeholder)
├── .gitignore          # Ignores .env and virtual environment
└── templates/
    └── index.html      # HTML upload form
```

---

## Notes

* The app uses **raw image bytes** with `Content-Type: application/octet-stream` to avoid Hugging Face API errors.
* You can swap the model in `.env` with other Hugging Face models, like the **“Not Banana”** model.
* The `.env` file is **not included in the repo** to keep your API key secure.
