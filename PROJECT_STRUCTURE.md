# HybridDualNetPath — Project Structure

Single source of truth. No duplicate folders.

```
HybridDualNetPath/                    # GitHub repo root
│
├── notebook/                         # ML training (Jupyter / Colab)
│   ├── IIITSURAT_MAJOR_PROJECT_UI22EC34.ipynb   # Main notebook
│   ├── NIRJALA_13.ipynb                       # Earlier version
│   └── README.md
│
├── outputs/                          # Training results (plots, JSON)
│   ├── confusion_matrix.png
│   ├── training_curves.png
│   ├── roc_curves.png
│   ├── gradcam_visualizations.png
│   └── results_summary.json
│
├── docs/                             # Research paper & documentation
│   └── README.md
│
├── scripts/                          # Utility scripts (not Django)
│   ├── push_to_github.ps1            # Git push helper
│   └── export_weights_from_colab.py  # Download weights from Colab
│
├── web/                              # Django web application
│   ├── config/                       # Settings, Celery, URLs, WSGI
│   │   └── settings/
│   │       ├── base.py
│   │       ├── dev.py
│   │       └── prod.py
│   ├── accounts/                     # Signup / login
│   ├── core/                         # Home, About, How-to-use pages
│   ├── scans/                        # Upload, history, Celery tasks
│   ├── inference/                    # Model, TTA, Grad-CAM++
│   ├── templates/                    # HTML (Bootstrap + HTMX)
│   ├── static/                       # CSS, JS
│   ├── weights/                      # final_model.pth (local only, gitignored)
│   ├── manage.py
│   ├── download_model.py             # Fetch weights from Google Drive
│   ├── requirements.txt              # Python deps for web app
│   ├── Procfile                      # Railway / Render processes
│   ├── render.yaml                   # Render blueprint
│   └── README.md                     # Web app setup & deploy guide
│
├── .gitignore
├── requirements.txt                  # Python deps for notebooks
├── README.md                         # Main project readme
└── PROJECT_STRUCTURE.md              # This file
```

## What was removed (duplicates)

- `neurofusenet_web/` — duplicate of `web/` (deleted)
- Root-level copy of notebook — use `notebook/` only
- Scattered scripts — consolidated under `scripts/`

## Quick commands

```bash
# Web app
cd web && python manage.py runserver

# Verify setup
cd web && python manage.py check_setup

# Download model weights
cd web && python download_model.py
```

## GitHub

https://github.com/Jarpula-Nirjala/HybridDualNetPath
