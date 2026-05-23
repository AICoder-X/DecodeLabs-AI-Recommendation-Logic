# AI RECOMMENDATION LOGIC

A simple yet functional **content-based recommendation engine** built using Python. This project demonstrates how AI recommendation systems work by matching user skills to job roles using TF-IDF weighting and Cosine Similarity — no external ML libraries required. The engine ranks career paths based on how closely a user's skills align with each role — making it a practical and educational intermediate-level project.

---

## 📌 Table of Contents

- [📖 Overview](#-overview)  
- [✨ Features](#-features)  
- [🛠️ Technologies Used](#️-technologies-used)
- [🚀 Code ](#code )  
- [🔧 Future Enhancements](#-future-enhancements)  

---

## 📖 Overview

This project is a **command-line based AI recommendation system** that uses **Content-Based Filtering** to map a user's skills to the most relevant tech career paths. It accepts a minimum of three skills as input, builds a weighted user profile using TF-IDF, and computes Cosine Similarity against 12 job role profiles to return the Top 3 best-matched careers.

It's an intermediate-level project to explore how recommendation engines work and lays the foundation for more advanced concepts like collaborative filtering and neural recommendation models.

---

## ✨ Features

- Dataset of 12 job roles with associated skill sets
- Implements TF-IDF weighting from scratch — no sklearn needed
- Computes Cosine Similarity manually using pure Python math
- Follows a strict 4-step ranking pipeline:
  - Ingestion → Scoring → Sorting → Filtering
- Returns Top 3 career matches with match percentage and matched skills
- Includes a Cold Start protection — handles empty profile vectors safely
- Includes a Demo Mode with 3 pre-set skill profiles
- Includes a Live Mode where the user enters their own skills interactively
- Accepts a minimum of 3 skills to ensure accurate matching

---

## 🛠️ Technologies Used

- **Language**: Python 3.x
- **Libraries**:
  - **math** — logarithm and square root for TF-IDF and Cosine Similarity
  - **collections.Counter** — counting term frequencies
- **Concepts**:
  - Content-Based Filtering
  - TF-IDF (Term Frequency — Inverse Document Frequency)
  - Cosine Similarity
  - Vector Space Model
  - IPO Model (Input → Process → Output)
- **IDE/Editor**: Visual Studio Code / Any Python-supported IDE

---
## 🚀 Code 

- **Objectives**:
  - In this code we are going to build an AI Recommendation System.
  - Our main Goal is to create a recommendation engine that maps user skills to the most relevant career paths.
  - Key Requirements are: take user input (skills or interests), match preferences using similarity logic, display recommended items.
  - In this code we learn the concepts of logic building, pattern matching, and recommendation system concepts.
- **Explanation**:
  - Firstly, we define a dataset **JOB_ROLES** — a dictionary where each key is a job role and the value is a list of required skills. This acts as our item database.
  - After that we build the TF-IDF engine using three functions. **compute_tf()** calculates how frequently each skill appears in a role's profile. compute_idf() penalizes skills that appear across many roles (generic skills like "python") and rewards rare, specific ones. compute_tfidf_vector() multiplies TF and IDF together to produce a weighted vector for any skill list.
  - Then we define the **cosine_similarity()** function which measures the angular alignment between two TF-IDF vectors. It computes the dot product divided by the product of both vector magnitudes. A score of 1 means perfect match, 0 means no overlap. Cold Start protection returns 0.0 if either vector is empty.
  - After that we define the **recommend()** function which runs the full 4-step pipeline. Step 1 ingests and sanitizes user skills. Step 2 scores every job role by computing cosine similarity against the user profile. Step 3 sorts all roles in descending order by score. Step 4 filters the list and returns only the Top-N results.
  - Then we define **display_recommendations()** which formats and prints the results with medal rankings, a visual progress bar, match percentage, and the list of matched skills.
  - After that we define **run_recommender()** which is the interactive live mode. It collects skills from the user one by one, enforces a minimum of 3 inputs, then calls the recommend pipeline and displays results.
  - We also define **demo()** which runs three pre-set skill profiles automatically to demonstrate the engine without user input — useful for testing in Colab or Jupyter.
  - At the end of the code we have the starting point of the program that calls demo and run_recommender functions.

## 🔧 Future Enhancements

- Add support for:
  - Loading job roles dynamically from a CSV or JSON file
  - Collaborative filtering to recommend based on similar users
  - GUI integration using Tkinter or a web-based frontend
- Expand the dataset with more job roles and skills
- Add a skill gap feature — show which skills to learn to improve match score
- Integrate with LinkedIn or job APIs to fetch real job postings
- Deploy as a web app using Flask or FastAPI

---
