[![DOI](https://zenodo.org/badge/582718021.svg)](https://zenodo.org/doi/10.5281/zenodo.12507163)

<h1 align="center">Diet Recommendation System</h1>
<div align= "center"><img src="Assets/logo_img1.jpg" />
  <h4>A diet recommendation web application using content-based approach with Scikit-Learn, FastAPI and Streamlit.</h4>
</div>

# Diet-Recommendation-System

## :bookmark_tabs:Table of contents
* [General info](#general-info)
* [Development](#development)
* [Technologies](#technologies)
* [Setup](#setup)

## :scroll: General info
### Motivation
People from all around the world are getting more concerned in their health and way of life in today's modern environment. However, avoiding junk food and exercising alone are insufficient; we also need to eat a balanced diet. We can live a healthy life with a balanced diet based on our height, weight, and age. Your diet can help you achieve and maintain a healthy weight, lower your chance of developing chronic diseases (including cancer and heart disease), and improve your general health when combined with physical activity. Nevertheless, there is a little SOTA project on food/diet recommendation system. Therefore I got the idea to build a content-based recommendation system for this purpose using machine learning. 
### What is a food recommendation engine?
A food recommendation engine using a content-based approach is an important tool for promoting healthy eating habits. This type of engine uses information about the nutritional content and ingredients of foods to make personalized recommendations to users. One of the key advantages of a content-based approach is that it takes into account an individual's dietary restrictions and preferences, such as allergies or food preferences. By providing users with tailored recommendations, a content-based food recommendation engine can help them make better choices about what to eat and improve their overall health. Additionally, by recommending a variety of healthy foods, it can also help users to discover new and nutritious options, expand their dietary horizons and overcome food boredom. All these can lead to a better and well-rounded diet, which can have a positive impact on long-term health outcomes.

### What is a content-based recommendation engine?
A content-based recommendation engine is a type of recommendation system that uses the characteristics or content of an item to recommend similar items to users. It works by analyzing the content of items, such as text, images, or audio, and identifying patterns or features that are associated with certain items. These patterns or features are then used to compare items and recommend similar ones to users.
<div align= "center"><img src="Assets/content_based_img.webp" /></div>

### Why content-based approach?

* No data from other users is required to start making recommendations.
* Recommendations are highly relevant to the user.
* Recommendations are transparent to the user.
* You avoid the “cold start” problem. 
* Content-based filtering systems are generally easier to create.

### Challenges of content-based approach
# Diet Recommendation Chatbot

This repository contains a diet recommendation system with a Streamlit frontend and a FastAPI backend. The recommendation engine uses a content-based approach with scikit-learn to suggest meals based on user information and nutritional features.

Repository layout

```
./
├─ FastAPI_Backend/         # FastAPI app and model code
├─ Streamlit_Frontend/      # Streamlit UI and pages
├─ Data/                    # Raw/enhanced datasets (large files)
├─ Assets/                  # Images and icons used by the UI
├─ docker-compose.yml
├─ README.md                # <- this file
└─ project_report.md
```

Quick start

1) Run locally (recommended for development)

 - Start the backend API:

   - Install dependencies (preferably in a virtualenv):

     pip install -r FastAPI_Backend/requirements.txt

   - Start FastAPI (from repository root):

     uvicorn FastAPI_Backend.main:app --reload --port 8000

 - Start the Streamlit frontend:

     pip install -r Streamlit_Frontend/requirements.txt
     streamlit run Streamlit_Frontend/Hello.py

 The Streamlit UI defaults to port 8501. The frontend talks to the backend API on the configured URL (see `Streamlit_Frontend/Generate_Recommendations.py` or app pages for the exact endpoint).

2) Run with Docker Compose (builds and runs both services)

   docker-compose up -d --build

 Then open http://localhost:8501 for the Streamlit UI.

Notes and recommendations

- Large data files: `Data/dataset.csv` and `Data/dataset_enhanced.csv` are ~90 MB each and have already been pushed to GitHub. GitHub warned about their size when pushing. For long-term maintenance you should consider one of the following:
  - Use Git LFS for these files (recommended) and re-add them under LFS tracking.
  - Move datasets to a separate releases storage (GitHub Releases, S3) and keep only a small sample in the repo.

- Repo structure: The frontend is under `Streamlit_Frontend/` with pages in `Streamlit_Frontend/pages/`. The backend FastAPI app is in `FastAPI_Backend/`.

Contributing

If you want to contribute, please fork the repo and open a pull request. Helpful contributions include:

- Adding tests and CI for the backend endpoints
- Moving large data to Git LFS or external storage
- Adding a small sample dataset in `Data/sample/` for CI and quick testing

Contact

If you want me to make any of the follow-ups for you (convert the large files to Git LFS, add CI, or update the README with badges and usage examples) I can do that next — tell me which you'd like.
