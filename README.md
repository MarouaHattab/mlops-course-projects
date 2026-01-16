# 🚀 MLOps Course Projects Portfolio

This repository contains a collection of projects developed during the **Master MLOps 2025-2026** course, taught by **Dr. Salah Gontara**. Each project focuses on a specific pillar of the MLOps lifecycle, from data versioning to automated pipelines and deployment.

---

## 📂 Project Structure

The portfolio is organized into specialized modules, each demonstrating a core MLOps concept:

### 📸 Computer Vision & YOLO (Deep Learning)
*   **[MLflow CV YOLO](./mlflow-cv-yolo)**: Experiment tracking with MLflow for YOLOv8 tiny. Comparison of runs, metrics logging, and model registry usage.
*   **[Optuna CV YOLO](./optuna-cv-yolo)**: Hyperparameter optimization using Optuna. Intelligent search strategies to maximize model performance (mAP).
*   **[ZenML CV YOLO](./zenml-cv-yolo)**: Full pipeline orchestration using ZenML. Integration of MLflow for tracking and MinIO for artifact storage.
*   **[Deploy CV YOLO](./deploy-cv-yolo)**: Serving YOLO models using TorchServe and Docker. Includes an API Gateway (FastAPI) and version management (v1/v2/rollback).

### 🌸 Tabular Data & Classic ML
*   **[MLops DVC Iris](./mlops-dvc-iris)**: Data versioning fundamentals using DVC and MinIO (S3-compatible storage).
*   **[Iris AI Service](./iris-ai-service)**: End-to-end service with a FastAPI backend and a React (Vite) frontend, fully containerized with Docker Compose.
*   **[Fraud Detection MLOps](./fraud-detection-mlops)**: Exploratory Data Analysis and initial steps for a fraud detection system.

---

## 🛠️ Technology Stack

| Category | Tools |
| :--- | :--- |
| **Orchestration** | ZenML |
| **Tracking** | MLflow |
| **Versioning** | DVC, Git |
| **Serving** | TorchServe, FastAPI |
| **Containers** | Docker, Docker Compose |
| **Optimization** | Optuna |
| **Storage** | MinIO (S3 Compatible) |
| **Frameworks** | PyTorch (YOLO), Scikit-Learn |
| **Frontend** | React, Vite |

---

## 🚀 Getting Started

Most projects follow a similar setup pattern:

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/MarouaHattab/mlops-course-projects.git
    cd mlops-course-projects
    ```

2.  **Explore a module**: Navigate to any subdirectory to find a specific `README.md` with detailed instructions on how to run that project.

3.  **Infrastructure**: Many projects rely on Docker Compose to spin up supporting services (MLflow, MinIO, ZenML):
    ```bash
    docker compose up -d
    ```

---

## 👨‍🏫 Acknowledgments

Special thanks to **Dr. Salah Gontara** for the guidance and course materials provided during the Master MLOps program.

---

## 📄 License

These projects are for educational purposes.
