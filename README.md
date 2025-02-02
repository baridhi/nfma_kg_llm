## nfma_kg_llm
This code aims to convert any input text into a knowledge graph using Large Language Models.

## What is a knowledge graph?
A knowledge graph is an organized representation of real-world entities and their relationships. It is typically stored in a graph database, which natively stores the relationships between data entities. Entities in a knowledge graph can represent objects, events, situations, or concepts. The relationships between these entities capture the context and meaning of how they are connected.
Source: https://neo4j.com/blog/what-is-knowledge-graph/

## Overview
The code creates a simple knowledge graph from a PDF/Word document. The process the general idea of producing a knowledge graph with some simplifications.

First, we split the body of text into chunks. Then we extract concepts mentioned within each chunk using an LLM. This performs better than identifying entities.

Assuming that the concepts that are mentioned in the vicinity of each other are related, the edges in the KG are chunk of text which mention the two connected texts.

Once the nodes (concepts) and the edges (text chunks) are calculated, it is easy to create a graph out of them using Python libraries.
This implementation can be replicated in a local computer and does not need GPUs. Using the sans-GPT approach makes it economical and efficient. The core underlying LLM used is the Mistral 7B openorca instruct.
Finally, the model can be set up locally using Ollama; so, generating the KG is free of cost becuase it does not rely on paid LLMs.


## Set-up for Ollama
Ollama is easy to run locally. Mistral 7B OpenOrca version is already available with Ollama to use out of the box.
To set up this project, you must install Ollama on your local machine.
Step 1: Install Ollama https://ollama.ai
Step 2: run ollama run zephyr in your terminal. This will pull the zephyr model to your local machine and start the Ollama server.
