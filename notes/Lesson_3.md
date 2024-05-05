# Preparing Text Data for RAG

- RAG systems are using text embeddings to match prompt to relevant sections within the unstructured data.
- Similarly to find text in knowledge graph, we'll need to create embeddings of the text fields in the graph.
- First step to enable vector search is to create vector index.

## Notebook

- [Jupyter Notebook](../code/L3-prep_text_for_RAG.ipynb)
- This notebook uses the movie database used in [previous lesson](./Lesson_2.md#notebook).
- [Pre-requisite](https://neo4j.com/docs/cypher-manual/current/genai-integrations/#_prerequisites): OpenAI account
- Signature for `genai.vector.encode()` is described in [GenAI integrations documentation](https://neo4j.com/docs/cypher-manual/current/genai-integrations/#single-embedding).
  - `genai.vector.encode(resource :: STRING, provider :: STRING, configuration :: MAP = {}) :: LIST<FLOAT>`
