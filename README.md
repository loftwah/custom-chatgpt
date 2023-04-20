# Custom ChatGPT

GPT-4 Enhanced Knowledge Base App integrates codebases, documentation, and knowledge bases with GPT-4. Features include data integration, text summarization, divide & conquer for long texts, custom prompts, caching, monitoring, adjustable response settings, and model updates. It overcomes GPT-4's limitations while delivering accurate responses.

GPT-4 Enhanced Knowledge Base Application

The GPT-4 Enhanced Knowledge Base Application is a powerful, AI-driven solution designed to address the limitations of GPT-4 while providing users with accurate and efficient responses. By integrating a user's codebase, documentation, and knowledge base with GPT-4, the application enables users to extract valuable insights and information in a user-friendly manner.

Key features of the GPT-4 Enhanced Knowledge Base Application include:

1. **Data Integration:** The application seamlessly integrates data from codebases, documentation, and knowledge bases into a searchable knowledge graph using Weaviate and PineconeDB for efficient retrieval and processing.
2. **Text Summarization:** The application employs a text summarization model trained with MindsDB or GPT-4 itself to condense input text, ensuring that the model can handle longer conversations or documents within its token limit.
3. **Divide and Conquer:** The application is capable of splitting lengthy documents or conversations into smaller chunks while preserving context, allowing GPT-4 to process and generate meaningful responses for each chunk.
4. **Prompt Engineering:** The application leverages custom prompts tailored to specific use cases, extracting the most relevant information from GPT-4 in the shortest possible response.
5. **Caching and Memoization:** The application stores and reuses the results of frequent queries or similar inputs, reducing redundant computation and improving response times.
6. **Monitoring and Control:** The application provides an intuitive dashboard to visualize API usage, response times, and other relevant metrics, enabling users to manage their budget effectively.
7. **Temperature and Top-P Settings:** Users can adjust the temperature and top-p settings to control the randomness and focus of generated responses, optimizing the balance between creativity and computational efficiency.
8. **Model Updates and Improvements:** The application tracks and adopts the latest GPT model improvements, ensuring users can take advantage of advancements in AI research.

With the GPT-4 Enhanced Knowledge Base Application, users can harness the full potential of GPT-4 in combination with their own codebase, documentation, and knowledge base, yielding accurate and efficient responses while overcoming the limitations of GPT-4.

## API

Here's an API design for your GPT-4 Enhanced Knowledge Base Application:

Base URL: `https://customgpt.deanlofts.xyz/v1`

Authentication: Bearer token or API key

Endpoints:

1. `/ingest` (POST)

   Ingests data (codebase, documentation, or knowledge base) into Weaviate and PineconeDB.

   Request body parameters:

   * `dataType`: Type of data being ingested (e.g., codebase, documentation, knowledge\_base)
   * `data`: The content to be ingested

   Response:

   * `status`: Success or failure status of the ingestion
   * `message`: Informational message about the ingestion process

2. `/query` (POST)

   Processes a query and returns the response.

   Request body parameters:

   * `query`: The user's query or input text
   * `temperature`: (Optional) A value to control the randomness of the generated response
   * `top_p`: (Optional) A value to control the focus of the generated response

   Response:

   * `status`: Success or failure status of the query processing
   * `response`: The generated response based on the input query

3. `/usage` (GET)

   Retrieves API usage statistics.

   Response:

   * `status`: Success or failure status of the request
   * `usage`: An object containing usage statistics (e.g., total requests, total tokens, average response time)

This API design allows you to build a GPT-4 Enhanced Knowledge Base Application that efficiently integrates GPT-4 with your codebase, documentation, and knowledge base, addressing GPT-4's limitations and providing accurate and efficient responses.

### Running the Application

1. Clone this repository:

```bash
git clone https://github.com/loftwah/custom-chatgpt.git
cd custom-chatgpt
```

1. Build the Docker image:

`docker build -t gpt4-enhanced-kb-app .`

1. Run the Docker container:

`docker run -it --rm --name gpt4-enhanced-kb-app-instance gpt4-enhanced-kb-app`

1. After the container starts, you can interact with the GPT-4 Enhanced Knowledge Base Application CLI.

### CLI Usage Examples

1. Ingest a codebase from a file:

```python
python gpt4_cli.py ingest --data-type codebase codebase_file.txt
```

1. Process a query with custom temperature and top-p settings:

```bash
python gpt4_cli.py query --temperature 0.8 --top-p 0.9 "What is the purpose of this function?"
```

1. Retrieve API usage statistics:

python gpt4_cli.py usage

## Acknowledgments

* OpenAI for the GPT-4 model
* Weaviate, PineconeDB, and MindsDB for data integration and processing
