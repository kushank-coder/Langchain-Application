# Lanchain-Application

Step 1: First load the external data source which you want to leverage ( also u need to give link or location of the dataset)
(there are 80+ types of data loaders in langchain, for eg choose 
loader = GenericLoader(
    YoutubeAudioLoader([url],save_dir),
    OpenAIWhisperParser()
) #youtubeaudioloader - converts video to audio 
#openaiwhisperparser - converts audio to text

Step2: Use loader.load() to load the dataset into your current python machine. For eg
docs = loader.load()

Step3: Now docs is a list object, where each page is a documnet. ie "docs" is a list of documents which will be leveraged

Step4: Each document has 2 attributes ....1 -> page_content  (main text) and 2nd -> source (what was the source for the document)
