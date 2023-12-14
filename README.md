# LGEN_Ambiguous_Queries
**This project is being conducted through my course: "CS 6998 Section 011: Language Generation and Summarization, Fall 2023" at Columbia University.**

## Commands
There are no main execution commands that are required to run this project. As long as you have the required libraries listed in the Jupyter notebook, you should be set.

## Dependencies
You will need specific dependencies to run this project. This project requires you to install Jupyter Notebook/Lab in order to run this project.

### PyTorch: 
  `pip install torch`
### sklearn:
  `pip install scikit-learn`
### nltk:
  `pip install nltk`
### openai:
  `pip install openai`
### HuggingFace/Transformers:
  `pip install transformers`

## Data
The dataset used can be found [here](https://nlp.cs.washington.edu/ambigqa/). In order to run the project, you will need to download the 'AmbigNQ (full ver.)' dataset. As far as storing the data, it is suggested to store it outside your repository folder from which you cloned this repository. The data should be stored in a folder named 'data'. Within this folder, there should be 3 folders: 'BERT', 'GPT, and 'LARGE'. This organization is important to minimize any issues while running the data processing jupyter notebooks. Currently, this is the second download link from the left in the row of data. The preprocessing done on the dataset is all included in this repository, so theoretically all you need to do is run the cells step by step. It is important to start out by running the jupyter notebooks under the 'data_processing' folder, then those under 'models' to fine-tune them, then those in the 'chatbot'. The data processing includes eliminanting NaN values, adding new features such as 'question type', splitting the data through a stratified split ultimately creating a test set, and the specific datasets for each of the models.

## Training
Once you run the data processing notebooks, you can more on to the fine-tuning notebooks. Running all of the notebooks should work, so the training should come easy. For the BART fine tuning, we are essentially fine-tuning based on ambiguous question to disambiguated question pairs. The code initializes a bart tokenizer and conditional generation model based on the 'facebook/bart-large' model. You are free to adjust the size of the batches and learning rates if you want to experiment with the models. Currently, the model trains off 5 epochs, but early stops around 3. For the BERT model, it is the same situation.

At this point, training for the baseline and experiments is the same, as training is the fine-tuning of the BERT and BART model. Tuning the GPT models is not necessary. When you run the code of the 'chatbot' jupyter notebook, all the code is included to process the data ready to work witht he GPT testing, including the RAG setup.

## Evaluation
There are four main chatbots in the chatbot ipynb depicted by sections in text cells, where the last cell in each section contains the lastest version of the chatbot. The ones above are experimental. The four chatbots include a demo for user interaction (which is the first chatbot cell) under the section 'Chatbot with Ambiguous Query Processing', a testing chatbot for ambiguous query processing and RAG, a testing chatbot without ambiguous query processing with RAG under 'Chatbot without Ambiguous Query Processing', and the final test chatbot with the vanilla GPT model under the section 'Chtbot without Ambiguous Processing & No RAG'. When evaluating the chatbot's performance, there are segments of code under the final versions of each chatbot section. These evaluations measure the average METEOR score and average BLEU, which are used to numerically compare the performances of the different chatbots. Sampling of the testing dataset is performed already in the 'Test Data Loading' section from the larger test dataset. Two dataframes are produced. One including the page contents and page content embeddings (which is used for the RAG system), and the sample test dataframe containing 100 samples of ambiguous questions and their expected answers.
