## Chat bot using Neo4j

---

## Tech stack used:

- langchain
- Neo4j
- LLM ollama llama2

---

## Project Setup Instructions

To install dependencies use:

```
pip install poetry
poetry install

```

To run ollama and neo4j, make sure to have docker installed and have wsl2 set up.

To run Ollama Llama2:
```
docker pull ollama/ollama
docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama
docker exec -it ollama ollama run llama2

```

To run Neo4j: If you have neo4j installed on the desktop, it makes it easier for visualization

```
docker run -p 7474:7474 -p 7687:7687 -v $PWD/data:/data -v $PWD/plugins:/plugins --name neo4j-apoc -e NEO4J_apoc_export_file_enabled=true -e NEO4J_apoc_import_file_enabled=true -e NEO4J_apoc_import_file_use__neo4j__config=true -e NEO4J_PLUGINS=\[\"apoc\"\] -e NEO4J_dbms_security_procedures_unrestricted=apoc.\\\* --env NEO4J_AUTH=neo4j/password neo4j

```

After this run every cell in the jupyter notebook.