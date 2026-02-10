# Elasticsearch Workshop

Welcome to the **Elasticsearch Workshop** repository!
This project is designed as a hands-on learning resource for working with **Elasticsearch using Python**.
It contains Jupyter notebooks, datasets, and slides that guide you from basic concepts to more advanced use cases.

---

## Repository contents

- `notebooks/` – Jupyter notebooks with practical Elasticsearch examples
- `slides/` – Presentation slides
- `data/` – Sample datasets used in the notebooks
- `pyproject.toml` – Project configuration and dependencies (managed by `uv`)

---

## Prerequisites

- Basic Python knowledge
- Familiarity with JSON and data structures
- [uv](https://docs.astral.sh/uv/) – fast Python package manager
- **Elasticsearch** running locally or remotely

### Running Elasticsearch locally (Docker / Podman)

```bash
docker run -d --name elasticsearch -p 9200:9200 \
  -e "discovery.type=single-node" \
  -e "xpack.security.enabled=false" \
  -e "xpack.license.self_generated.type=trial" \
  -v elasticsearch-data:/usr/share/elasticsearch/data \
  docker.elastic.co/elasticsearch/elasticsearch:8.15.0
```

Elasticsearch will be available at:
`http://localhost:9200`

---

## Getting started

### 1. Clone the repository

```bash
git clone https://github.com/vitezslavjira-ACE/ElasticSearch_Workshop
cd ElasticSearch_Workshop
```

---

### 2. Install dependencies

```bash
uv sync
```

This installs core dependencies and dev tools (JupyterLab, ipykernel).

To also install machine learning dependencies (sentence-transformers):

```bash
uv sync --group ml
```

> ML dependencies are separated into a dedicated group to keep the base setup lightweight.

---

### 3. Set up Jupyter kernel

```bash
uv run python -m ipykernel install --user --name es-workshop --display-name "ES Workshop (uv)"
```

This ensures that Jupyter notebooks run using the correct virtual environment.

---

## Working with notebooks

### Option A: VS Code (recommended)

Install the following extensions:
- **Python** (Microsoft)
- **Jupyter** (Microsoft)

Open the repository folder in VS Code, then:
- open any notebook from `notebooks/`
- select the **ES Workshop (uv)** kernel if prompted

---

### Option B: JupyterLab

```bash
uv run jupyter lab
```

Then select the **ES Workshop (uv)** kernel inside the notebook UI.

---

### Option C: Classic Jupyter Notebook

```bash
uv run jupyter notebook
```

---

## Sanity check (recommended)

Run this as the first cell in any notebook:

```python
import sys
print(sys.executable)

from sentence_transformers import SentenceTransformer
model = SentenceTransformer("all-MiniLM-L6-v2")
print("Environment OK")
```

You should see a path pointing to `.venv` and no import errors.

---

## Notes & best practices

- If something breaks badly, removing `.venv` and running `uv sync` again is often faster than debugging
- ML dependencies are intentionally in a separate group (`uv sync --group ml`)

---

Happy learning, and enjoy your journey into Elasticsearch!
