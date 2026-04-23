# 🎬 Movie Recommendation System

A full-stack, AI-powered movie recommendation system built with **FastAPI** and **Streamlit**. It uses content-based filtering (TF-IDF and Cosine Similarity) along with real-time data from **The Movie Database (TMDB) API** to provide highly accurate and dynamic movie recommendations.

## ✨ Features
- **Dynamic Home Feed:** View trending, popular, top-rated, upcoming, and now-playing movies directly on the home page.
- **Smart Search Engine:** Fast autocomplete search that matches movie titles and shows instant posters.
- **Detailed Movie Information:** View overviews, release dates, genres, posters, and backdrop images.
- **Dual Recommendation Engine:**
  - **Content-Based (TF-IDF):** Recommends movies locally based on plot/metadata similarity.
  - **Genre-Based:** Recommends similar movies by matching genres dynamically from TMDB.
- **Modern UI:** Clean, responsive, and aesthetic user interface powered by Streamlit.

## 🛠️ Technology Stack
- **Frontend:** Streamlit
- **Backend:** FastAPI, Uvicorn
- **Machine Learning:** Scikit-learn (TF-IDF, Cosine Similarity), Pandas, NumPy
- **External API:** TMDB (The Movie Database) API
- **Data Persistence:** Python Pickle (`.pkl`) for fast matrix and dataframe loading

---

## 🚀 Step-by-Step Setup Guide

Follow these instructions to run the application locally on your machine.

### 1. Prerequisites
Ensure you have the following installed:
- [Python 3.8+](https://www.python.org/downloads/)
- A TMDB API Key. You can get one for free by creating an account at [The Movie Database](https://www.themoviedb.org/).

### 2. Clone or Navigate to the Project
```bash
git clone https://github.com/DivyajChhajed/YourRepository.git
cd YourRepository
```
*(If you have downloaded the files locally instead, simply open your terminal and navigate to the project folder.)*

### 3. Create a Virtual Environment
It is highly recommended to use a virtual environment to manage project dependencies.
```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment (Windows PowerShell)
.\venv\Scripts\activate

# Activate virtual environment (Mac/Linux)
source venv/bin/activate
```
*(Note: If you get an execution policy error on Windows, run `Set-ExecutionPolicy Unrestricted -Scope Process` first).*

### 4. Install Dependencies
Install all the required Python packages from the `requirements.txt` file:
```bash
pip install -r requirements.txt
```

### 5. Set up Environment Variables
The application requires your TMDB API key to fetch live movie data and posters. 
Create a file named `.env` in the root directory of the project and add your API key:
```env
TMDB_API_KEY=your_actual_tmdb_api_key_here
```

### 6. Start the FastAPI Backend
Start the backend server using Uvicorn. This will load the pre-computed machine learning models (`.pkl` files) into memory and expose the API endpoints.
```bash
uvicorn main:app --reload
```
*The backend API will run at `http://127.0.0.1:8000`. **Keep this terminal window open.***

### 7. Start the Streamlit Frontend
Open a **new terminal window**, activate your virtual environment again, and run the Streamlit app:
```bash
# Don't forget to activate the venv again in the new terminal!
.\venv\Scripts\activate

# Run the app
streamlit run app.py
```
*Your browser will automatically open the application, usually at `http://localhost:8501`.*

---

## 📁 Project Structure
- `app.py`: Streamlit frontend UI and routing logic.
- `main.py`: FastAPI backend, API endpoints, and ML model loading.
- `requirements.txt`: Python package dependencies.
- `.env`: Secret environment variables (TMDB API Key).
- `movies.ipynb`: Jupyter notebook containing the data processing and ML model training steps.
- `*.pkl`: Pre-computed data structures for the TF-IDF recommendation engine (Dataframe, indices, matrix).

## 📝 License
This project is open-source and available under the MIT License.
