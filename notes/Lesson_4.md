# Constructing a Knowledge Graph from Text Documents

## SEC filing data

- **10-K**: Out of the many financial reports that companies are required to file with the SEC each year, 10-K is an important form which is an annual report of the companies activities.
- Publicly accessed through the SEC's EDGAR database.

## Data cleaning

- Completed 10-K forms are available to download as text files that contain XML components.
- Following cleanup steps were applied to create the json data dump in this course:
  - Cleaned up files using regex
  - Parsed XML into Python data structures using Beautiful Soup
  - Extracted CIK (Central Index Key): Company identifier used by the SEC
  - Extracted specific sections of the form (Items 1, 1a, 7 and 7a)

## Plan of attack

1. Split form sections into chunks using a LangChain textsplitter.
2. Create a graph where each chunk is a node, adding chunk metadata as properties.
3. Create a vector index.
4. Calculate the text embedding vector for each chunk and populate the index.
5. Use similarity search to find relevant chunks.

## Neo4j documentation

- [MERGE command](https://neo4j.com/docs/cypher-manual/current/clauses/merge/)
- [Vector index commands](https://neo4j.com/docs/cypher-manual/current/indexes/semantic-indexes/vector-indexes/#_vector_index_commands_and_procedures)

## Summary

- In this lesson, we have used Neo4j more as a vector store rather than Knowledge Graph.

## Notebook

- [Jupyter Notebook](../code/L4-construct_kg_from_text.ipynb)
- Issue faced:
  - `ModuleNotFoundError: No module named 'langchain_openai'`
  - [Solution](https://stackoverflow.com/questions/77782167/modulenotfounderror-no-module-named-langchain-openai): `pip install langchain-openai`
- Neo4j vector interface
  - Easiest way to start using Neo4j with LangChain
  - This makes Neo4j look like a vector store
  - Under the hood, uses Cupher language to perform vector similarity search
  - `RetrievalQAWithSourcesChain`
    - Used in chatbot for Question-Answer type of interaction.
  