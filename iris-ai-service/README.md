# Projet : API FastAPI + Frontend React (Docker / Docker Compose)

## Objectif

Déployer un modèle IA (Iris – RandomForest) via une **API FastAPI** et un **Frontend React**, chacun dans un conteneur séparé, orchestrés avec **Docker Compose**.

---

## Fonctionnement attendu

1. Le modèle (`model.joblib` et `model_metadata.json`) est placé dans `api/app/model/`.
2. L’API charge le modèle et expose :

   * `GET /health` → état du modèle
   * `POST /predict` → renvoie la classe prédite et les probabilités
3. Le Frontend envoie les données (sepal/petal) et affiche la prédiction.
4. L’ensemble est lancé avec :

   ```bash
   docker compose up --build
   ```

---

## Fichiers à créer

### `api/Dockerfile`

* Image de base : `python:3.11-slim`
* Installer les dépendances depuis `requirements.txt`
* Copier le dossier `app/`
* Exposer le port `8000`
* Commande de lancement :

  ```bash
  uvicorn app.main:app --host 0.0.0.0 --port 8000
  ```

### `frontend/Dockerfile`

* Étape 1 : build du frontend (`node:20-alpine`)

  * Installer les dépendances
  * Exécuter `npm run build`
* Étape 2 : servir le site avec `nginx:alpine`

  * Copier le dossier `dist` vers `/usr/share/nginx/html`
  * Exposer le port `80`

### `docker-compose.yml`

* Deux services :

  * `api` → build depuis `./api`, port `8000`
  * `frontend` → build depuis `./frontend`, port `5174`, dépend de `api`
* Variables d’environnement :

  ```
  API_PORT=8000
  CORS_ORIGINS=http://localhost:5174
  VITE_API_BASE=http://localhost:8000
  ```

---
