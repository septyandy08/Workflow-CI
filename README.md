# Workflow-CI — SMSML Personality

Repository ini berisi MLflow Project + GitHub Actions workflow untuk
otomatisasi re-training model klasifikasi kepribadian (Extrovert vs
Introvert) **setiap push ke `main`** atau saat dipantik manual.

## Struktur

```
Workflow-CI/
├── .github/workflows/ci.yml      # GitHub Actions CI
├── MLProject/
│   ├── MLProject                  # Definisi MLflow Project
│   ├── conda.yaml                 # Environment conda
│   ├── modelling.py               # Entry point training
│   └── personality_preprocessing/ # Dataset hasil preprocessing
├── DockerHub.txt                  # Tautan ke Docker Hub image
└── README.md
```

## Cara menjalankan lokal

```bash
cd MLProject
mlflow run . --env-manager=local \
  -P data_dir=personality_preprocessing \
  -P n_estimators=300 -P max_depth=12
```
