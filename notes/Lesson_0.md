# Introduction

- Example
  - Employer-Employee relationship
    - Person node: Stores individual's name, email etc.
    - Company node: Stores Number of employees, revenue etc.
    - Relationship represented by an edge between these nodes.
      - Stores additional information about the employment relationship.
      - e.g. Person's job title, start date etc.

- Knowledge graphs make it much easier to represent and search deep relationships which enables much faster execution of queries.
- Web search engines and e-commerce websites have found knowledge graphs a key technology for delivering relevant results.

- Combine Knowledge Graph with an embedding model
  - Creates a powerful tool for carrying out RAG with LLM
  - Takes advantage of the relationships and metadata stored in the graph to improve the relevance of the text you retrieve and pass to the language model.

- Advantages of storing text chunks in a Knowledge Graph over Similarity Search with text embeddings
  - You can retrieve one chunk and then traverse the graph to find out other relevant chunks which gives more context.

- What's in the course?
  - Build a Knowledge Graph to represent one set of SEC forms and use LangChain to carry out RAG by retrieving text from this graph.
  - Build another Knowledge Graph from second set of SEC forms.
  - Then connect the two graphs using some linking data.
