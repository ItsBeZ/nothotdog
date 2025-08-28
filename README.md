# Not Hot Dog Web App 🍔❌🌭

This is a simple web application built with **Flask** that detects whether an image is a **hot dog** or **not a hot dog** using a **Hugging Face machine learning model**.  

It’s inspired by the classic "Hot Dog or Not Hot Dog" app from *Silicon Valley*.  

---

## Features

- Upload an image via a simple web interface.
- Sends the image to a Hugging Face model for classification.
- Returns a prediction indicating whether the image is a hot dog or not.
- Safe API key handling using `.env` files.

---

## Demo

After running locally, open your browser at:

http://127.0.0.1:5000/

yaml
Copy code

Upload an image to see the prediction.

---

## Setup Instructions (Windows)

### 1. Clone the repository

```bash
git clone https://github.com/<YourUsername>/nothotdog.git
cd nothotdog
2. Create a virtual environment
cmd
Copy code
python -m venv .venv
.venv\Scripts\activate
3. Install required packages
c
Copy code
pip install flask python-dotenv requests
4. Create a .env file
Copy .env.example to .env:

cmd
Copy code
copy .env.example .env
Add your Hugging Face API key:

ini
Copy code
HUGGING_FACE_API_URL=https://api-inference.huggingface.co/models/julien-c/hotdog-not-hotdog
HUGGING_FACE_API_KEY=your_hugging_face_api_key_here
Important: Do not push .env to GitHub. The .gitignore already prevents this.

5. Run the app
c
Copy code
python web.py
Open your browser at http://127.0.0.1:5000/ and start testing!

File Structure
bash
Copy code
nothotdog/
│
├── web.py              # Flask server code
├── .env.example        # Example environment variables (API key placeholder)
├── .gitignore          # Ignores .env and virtual environment
└── templates/
    └── index.html      # HTML upload form
Notes
The app uses raw image bytes with Content-Type: application/octet-stream to avoid Hugging Face API errors.

You can swap the model in .env with other Hugging Face models, like the “Not Banana” model.

The .env file is not included in the repo to keep your API key secure.

License
This project is open-source. Feel free to use and modify it for educational purposes.