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

2. Install the required dependencies (to a new venv):

    ```bash
    pip install -r requirements.txt
    ```

3. Open the notebooks in the `notebooks/` directory and start learning!

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
