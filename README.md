# Elasticsearch Python Tutorial

Welcome to the Elasticsearch workshop repository! This resource is designed to help you get better at Elasticsearch using the Python client. Inside, you'll find notebooks and slides to guide you through the learning process.

## Repository contents

- `notebooks/`: Jupyter notebooks with hands-on Elasticsearch examples.
- `slides/`: Presentation slides used in the YouTube series.
- `data/`: Datasets.

## Getting started

1. Clone this repository:

    ```bash
    git clone https://github.com/vitezslavjira-ACE/ElasticSearch_Workshop
    ```

2. Create a virtual environment:

    ```bash
    py -m venv .venv
    ```

3. Activate the virtual environment:

    ```powershell
    .\.venv\Scripts\Activate.ps1
    ```

4. Install the required dependencies:

    ```bash
    pip install -r requirements.txt
    ```

5. Set up your Jupyter notebook environment:

    This course uses Jupyter notebooks extensively. You can work with them in several ways:
    
    - **VS Code** (recommended): Install the following extensions:
        - Python (by Microsoft)
        - Jupyter (by Microsoft)
        
        VS Code will automatically detect your `.venv` environment. Just open a notebook file and select the Python interpreter from your virtual environment when prompted.
    
    - **JupyterLab**: Run `jupyter lab` in your activated virtual environment
    - **Jupyter Notebook**: Run `jupyter notebook` in your activated virtual environment

6. Open the notebooks in the `notebooks/` directory and start learning!

## Prerequisites

- Basic Python knowledge
- Familiarity with data structures and JSON
- Elasticsearch installed locally or access to a remote instance. To install Elasticsearch locally, you need Docker Desktop. Run the following command:

    ```bash
    docker run -d --name elasticsearch -p 9200:9200 \
      -e "discovery.type=single-node" \
      -e "xpack.security.enabled=false" \
      -e "xpack.license.self_generated.type=trial" \
      -v elasticsearch-data:/usr/share/elasticsearch/data \
      docker.elastic.co/elasticsearch/elasticsearch:8.15.0
    ```

Happy learning, and enjoy your journey into Elasticsearch!
