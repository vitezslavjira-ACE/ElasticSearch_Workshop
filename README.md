# Elasticsearch Workshop

Welcome to the **Elasticsearch Workshop** repository!  
This project is designed as a hands-on learning resource for working with **Elasticsearch using Python**.  
It contains Jupyter notebooks, datasets, and slides that guide you from basic concepts to more advanced use cases.

---

## Repository contents

- `notebooks/` – Jupyter notebooks with practical Elasticsearch examples  
- `slides/` – Presentation slides  
- `data/` – Sample datasets used in the notebooks  
- `requirements.txt` – Core project dependencies  
- `requirements-ml.txt` – Machine learning dependencies  

---

## Prerequisites

- Basic Python knowledge  
- Familiarity with JSON and data structures  
- **Elasticsearch** running locally or remotely  

### Python version

Recommended: Python 3.12.10. On newer Python versions (e.g. 3.14), you may hit installation issues with missing C++ libraries (for example around the `elasticsearch` package). Python 3.11 will likely work as well. The versions in `requirements.txt` and `requirements-ml.txt` are pinned to match the Elasticsearch version used in Docker, so the Python in your `.venv` needs to be compatible with those pinned packages.

### Running Elasticsearch locally (Docker)

You need Docker Desktop installed. Then run:

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

### 1️⃣ Clone the repository

```bash
git clone https://github.com/vitezslavjira-ACE/ElasticSearch_Workshop
cd ElasticSearch_Workshop
```

---

### 2️⃣ Create a virtual environment

```bash
py -m venv .venv
```

---

### 3️⃣ Activate the virtual environment (Windows)

```cmd
.\.venv\Scripts\activate.bat
```

You should see:

```text
(.venv) C:\...\ElasticSearch_Workshop>
```

---

### 4️⃣ Upgrade installation tools

```bash
python -m pip install -U pip setuptools wheel
```

This step is **crucial**, especially when installing ML-related packages.

---

### 5️⃣ Install core dependencies

```bash
python -m pip install -r requirements.txt
```

These are the minimal dependencies required to run the workshop notebooks and API examples.

---

### 6️⃣ Install machine learning dependencies

Some notebooks use sentence embeddings and semantic search.

```bash
python -m pip install -r requirements-ml.txt
```

> ML dependencies are intentionally separated to keep the base setup lightweight and stable.

---

### 7️⃣ Set up Jupyter kernel for the virtual environment

```bash
python -m pip install ipykernel
python -m ipykernel install --user --name es-workshop --display-name "ES Workshop (.venv)"
```

This ensures that Jupyter notebooks always run using the correct virtual environment.

---

## Working with notebooks

### Option A: VS Code (recommended)

Install the following extensions:
- **Python** (Microsoft)
- **Jupyter** (Microsoft)

Open the repository folder in VS Code, then:
- open any notebook from `notebooks/`
- select the **ES Workshop (.venv)** kernel if prompted

VS Code will reuse this kernel for all notebooks in the project.

---

### Option B: JupyterLab

```bash
jupyter lab
```

Then select the **ES Workshop (.venv)** kernel inside the notebook UI.

---

### Option C: Classic Jupyter Notebook

```bash
jupyter notebook
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

Then use "Run All" (run all cells) in:
- `notebooks/3_create_index.ipynb`
- `notebooks/16_embeddings.ipynb`
This should complete without any import-related errors.

---

## Notes & best practices

- Do **not** interrupt `pip install` when installing ML packages  
- If something breaks badly, deleting `.venv` and recreating it is often faster than fixing it  
- ML dependencies are intentionally not part of `requirements.txt`

---

Happy learning, and enjoy your journey into Elasticsearch 🚀
