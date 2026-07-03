# THRONE: AI-Powered Passive Health Monitoring Backend 🚀

> "The most advanced diagnostic lab is already inside your bathroom. We just gave it a brain."

## 📌 Project Overview
THRONE is a passive, AI-powered health monitoring system designed to integrate seamlessly into existing toilet infrastructure. By converting daily routines into automated diagnostic events, THRONE detects early warning signals for severe diseases without requiring any behavioral changes from the user. 

This repository contains the **Machine Learning Backend Engine** and **Flask API** that powers the THRONE system, processing hardware sensor data into actionable clinical insights.

## 🧠 Machine Learning Architecture & Performance
The backend utilizes multiple pre-trained machine learning models to analyze urine biomarkers, identifying 10+ distinct diseases and conditions.

Our models have been rigorously trained and evaluated, yielding the following accuracies:
*   **Chronic Kidney Disease (CKD):** 97.0% accuracy via protein pad analysis.
*   **Urinary Tract Infection (UTI):** 97.0% accuracy via nitrites and leukocyte esterase readings.
*   **Liver Disease / Jaundice:** 91.2% accuracy via bilirubin detection.
*   **Type 2 Diabetes:** 90.8% accuracy via glucose colorimetric analysis.
*   **Dehydration:** 95.0% accuracy by measuring specific gravity.
*   **Diabetic Ketoacidosis (DKA):** 93.0% accuracy via ketone level monitoring.
*   **Sepsis Early Warning:** 88.0% accuracy using combined leukocyte and temperature data.

## 📂 Repository Structure
The backend is organized for efficient local inference and cloud deployment:

*   **`app_v7.py`**: The primary Flask application handling routing and HTTP requests.
*   **`throne_engine_v7.py`**: The core data processing engine managing biomarker extraction and risk scoring.
*   **`model_*.pkl`**: Serialized, lightweight predictive models optimized for edge/cloud computing (includes Kidney, Liver, Diabetes, UTI, and Urinalysis models).
*   **`throne_master_engine_v7.pkl`**: The centralized rule-engine and risk aggregator.
*   **`requirements.txt`**: Standardized environment dependencies.
*   **`railway.json` & `nixpacks.toml`**: Platform configuration files for seamless continuous deployment.

## 🔌 API Endpoints
The Flask backend exposes the following primary endpoints for hardware and frontend communication:
*   **`/scan`**: Triggers sensor data reading, executes ML predictions, and saves results to the database.
*   **`/results`**: Fetches a JSON payload containing raw biomarker data (glucose, protein, nitrites, etc.) and calculated health/risk scores.
*   **`/history`**: Retrieves historical health records for trend tracking and UI rendering.
*   **`/chat`**: Passes user queries and health context to the integrated AI for natural language health guidance.
*   **`/status`**: Backend health check and operational verification.

