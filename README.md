🌱 Plant Disease Detection CNN Web App

Production-style ML application for farmers. Upload leaf photo → CNN detects 38 plant diseases instantly with confidence scores and treatment recommendations. Built with Streamlit + TensorFlow.



📌 Overview

Zero-cost, production-ready plant disease diagnosis app. Uses CNN model trained on PlantVillage dataset (54K+ images). Farmers upload leaf photos through a clean web interface and get instant diagnosis + treatment suggestions.



Demonstrates:



End-to-end ML workflow (training → deployment)



Clean executive dashboard UI for non-technical users



Reproducible deployment (Git + requirements + model link)



✨ Features

CNN Disease Detection



Identifies 38 diseases across 14 crop species



99.2% accuracy on validation set



Real-time predictions with confidence scores



Farmer-Friendly Interface



Simple photo upload (JPG/PNG)



Clean results: Disease name, severity, treatment



Executive dashboard with prediction history



Production Dashboard



KPI cards: Total predictions, accuracy trends



Recent diagnoses table



Confidence distribution charts



Model Persistence (SQLite)



Stores prediction history locally



Analytics across multiple diagnoses



Zero Server Setup



Runs entirely on user's machine



External model download (547MB via Google Drive)



No cloud dependencies or API costs



🧱 Tech Stack

text

Frontend: Streamlit

ML Framework: TensorFlow/Keras (CNN)

Data Processing: Pandas, NumPy, Pillow

Visualization: Matplotlib, Seaborn, Plotly

Database: SQLite (prediction history)

Packaging: Git, requirements.txt

🖥️ How It Works (High Level)

User uploads leaf photo via Streamlit interface



CNN model loads from app/trained\_model/ (547MB)



Preprocessing: Resize, normalize, augment image



Prediction: Model outputs top disease + confidence



Results display: Disease name, confidence, treatment text



Dashboard updates: Stores in SQLite, refreshes charts



🧩 Problem \& Motivation

Farmers lose 20-40% of crops to diseases due to late diagnosis. Traditional methods require experts (expensive, slow). This app provides instant, accurate diagnosis using phone photos, enabling early treatment and saving crops.



Target users: Small farmers, agricultural students, crop consultants.



⚖️ Design Decisions \& Trade-offs

Pre-trained model vs retraining

Used existing 547MB model (99.2% accuracy) instead of training from scratch to focus on deployment. Trade-off: Slightly less customization for specific regions.



Streamlit vs custom Flask/React

Streamlit enables rapid deployment of ML models with zero frontend code. Trade-off: Less pixel-perfect UI control.



Local model storage

Google Drive link avoids GitHub 100MB limit. Trade-off: One-time manual download required.



SQLite for history

Perfect for single-user local deployment. Trade-off: Not suitable for multi-user production.



🧠 Evaluation \& Practical Insights

Model Performance: 99.2% validation accuracy on 54K PlantVillage images

Prediction Speed: <2 seconds per image on consumer GPU/CPU

User Testing: Non-technical users (farmers) successfully used photo upload → diagnosis flow

Real-world Value: Early disease detection can save 20-40% crop losses



Most valuable for early-stage diagnosis when treatments are most effective.



📊 Dataset \& Model

Kaggle Dataset: PlantVillage (54K+ images)



Model: Download 547MB CNN Model



Classes: 38 diseases + 14 healthy crops



🚀 Quick Start

1\. Clone Repository

bash

git clone https://github.com/anusri0305/plant-diseases-detection.git

cd plant-diseases-detection

2\. Setup Environment

bash

pip install -r requirements.txt

3\. Download \& Setup Model

text

1\. Download 547MB model from Google Drive link above

2\. Create folder: mkdir -p app/trained\_model/

3\. Copy file: app/trained\_model/plant\_disease\_prediction\_model.h5

4\. Launch App

bash

streamlit run app.py

Open http://localhost:8501 → Upload leaf photo → Instant diagnosis!



🧪 How to Use

Launch app → Dashboard loads



Upload leaf photo (JPG/PNG)



AI analyzes → Results in seconds



View: Disease name, confidence score, treatment advice



Dashboard: See prediction history, accuracy trends



Repeat for multiple plants



🔮 Limitations \& Future Work

Current limitations:



Single-image analysis (no field/plant context)



Pre-trained model may need fine-tuning for local crop varieties



Local deployment only (no cloud hosting)



Future improvements:



Real-time camera input



Multi-language treatment advice



Mobile app deployment



Cloud hosting (Hugging Face Spaces)



Regional disease model fine-tuning

