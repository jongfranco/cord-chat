# cord-chat
This proof of concept is based on the CORVID-19 KAGGLE challenge https://www.kaggle.com/covid19 It provides a simple chatbot question answering functionality to answer COVID-19 queries based on ~30000 papers provided for this challenges.

The notebook does not apply fine tuning, it applies a pre-trained NLP model from e.g. the sentence-transformers project. The notebook embeds the challenge's COVID 19 papers' paragraphs (from the abstracts or the fulltexts) into a corpus of embeddings. The papers had been pre-processed for the challenge, i.e. converted from source format (e.g. pdf) into a json file based on which this notebook trains. The papers and the according licenses can be found via https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge.

After training (or loading a pre-trained model), the user can ask a question via the ask_question function. That returns the five sentences of all corpus that are closest.

Future enhancement: we could return the paper id in addition

Requires several standard packages, tqdm, sentence-transformers, scipy, torch (if allenai's scibert transformer model is used), transformer (if allenai's scibert transformer model is used), and iPython


Due to size restrictions, only the small corpus based on the papers' abstracts is uploaded. Hence, the notebook would automatically create the corpus embeddings using a transformer network. This step takes some time (hence the embeddings are stored in a file) 

Questions to CORVID-19 can be asked via ask_question. The best matching paragraphs in the corpus (i.e. the abstracts) are returned. 
This should either be used as the response or lead to further investigation of the returned papers - e.g. by checking the references, related papers etc.
