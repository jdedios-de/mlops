# mlops-prompt-sync-github

A minimal MLOps utility that syncs a local `prompt_manifest.json` file to a GitHub repository using a webhook. 
This is useful for prompt engineering workflows where prompt versioning and syncing are automated.

## Features

- Sync `prompt_manifest.json` via GitHub webhook
- Lightweight and easy to set up
- `.env` configuration for secrets and settings
- Python-based, minimal dependencies

## File Structure

```bash
.
├── .env                   # Environment variables (e.g., GitHub token, repo)
├── main.py                # Main Python script handling the webhook and sync
├── prompt_manifest.json   # Prompt definition to be synced
├── requirements.txt       # Python dependencies
└── README.md              # Project documentation
```

## Getting Started

### Prerequisites

- Python 3.8+
- GitHub personal access token
- GitHub repository

### Installation

1. Clone the repository:

```bash
git clone git@github.com:jdedios-de/mlops-prompt-sync-github.git
cd mlops-prompt-sync-github
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Configure the `.env` file:

```ini
GITHUB_TOKEN=your_github_token
REPO_NAME=username/repo-name
WEBHOOK_SECRET=your_webhook_secret
```

### Run
Deploy it to render.com

```bash
uvicorn main:app --host 0.0.0.0 --port $PORT
```
The script listens for a webhook trigger and syncs the latest `prompt_manifest.json` to the specified GitHub repo.

