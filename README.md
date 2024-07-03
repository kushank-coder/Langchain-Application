# Langchain-Application

Step 1: First load the external data source which you want to leverage ( also u need to give link or location of the dataset)
(there are 80+ types of data loaders in langchain, for eg choose 
loader = GenericLoader(
    YoutubeAudioLoader([url],save_dir),
    OpenAIWhisperParser()) #youtubeaudioloader - converts video to audio 

##openaiwhisperparser - converts audio to text
##PyPDFLoader - pds docs
##WebBaseLoader - any url 


Step2: Use loader.load() to load the dataset into your current python machine. For eg
docs = loader.load()

Step3: Now docs is a list object, where each page is a document. ie "docs" is a list of documents which will be leveraged

Step4: Each document has 2 attributes ....1 -> page_content  (main text) and 2nd -> source (what was the source for the document also known as metadata)



Step 5 Document Splitting into smaller chunks

Step 6 Store the chunks and their embeddings in the vector database

Step 7) Retrieve documents from vector database (by using retriever ex - Self Query Retriever, Compression LLM Retriever, MMR (maximum marginal relevance, Basic Similarity Search))

##Note Search operation is always done on vector database ie vector_db.similarity_search() or vector_db.max_marginal_relevance etc
