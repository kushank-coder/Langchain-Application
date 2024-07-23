# Langchain-Application

Step 1: First load the external data source to the langchain environment by using specific Loader 
(there are 80+ types of data loaders in langchain, for eg choose 
loader = GenericLoader(
    YoutubeAudioLoader([url],save_dir),
    OpenAIWhisperParser()) #youtubeaudioloader - converts video to audio)

##openaiwhisperparser - converts audio to text
##PyPDFLoader - pds docs
##WebBaseLoader - any url 


Step2: Use loader.load() to load the dataset into your current python machine. This will be the list of documents

docs = loader.load()

Step3: In docs list each element is of document type in lagchain interface, where each page is a document.

Step4: Each document has 2 attributes ....1 -> page_content  (main text) and 
										2nd -> source (what was the source for the document also known as metadata (location specific to the document))

Step 5
## Now Data is Loaded (on which langchain uses as base data from which info will come (info source)), now we need to 
		5.1) split the document pages into smaller chunks
		5.2) make embeddings by using hugging face or open ai embeddings
		5.3) Store the chunks and their corresponding embeddings in a vector space (vector space == a dictionary where key is chunks and values are embeddings)
		5.4) take the question from the user about what questions he wants to ask?
		5.5) Retrieve relevant chunks from vector embeddings. This can be done by various methods like (MMR : Max marginal relevance, similarity search, compressed LLMs , etc)
		5.6) Now we have the model by which we could question the document. 


Step 5 Document Splitting into smaller chunks

Step 6 Store the chunks and their embeddings in the vector database

Step 7) Retrieve documents from vector database (by using retriever ex - Self Query Retriever, Compression LLM Retriever, MMR (maximum marginal relevance, Basic Similarity Search))

##Note Search operation is always done on vector database ie vector_db.similarity_search() or vector_db.max_marginal_relevance etc
