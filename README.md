# LGEN_Ambiguous_Queries
**This project is being conducted through my course: "CS 6998 Section 011: Language Generation and Summarization, Fall 2023" at Columbia University.**

## Project Proposal
### Description
With the recent widespread recognition of the capabilities with GPT models, one of the biggest questions that arose was how can devel- opers produce question-answer chatbots of a particular topic, specifically data outside the pre-trained dataset. While there have been clever solutions to using OpenAI’s API and var- ious prompt-engineering techniques and parsed data, a key challenge is when these systems encounter ambiguous questions. During my Data Science internship at Canary Medical Inc., I developed a customer service chatbot that was customized using prompt engineering tech- niques to comprehend company-specific infor- mation. Notably, this information was not in- herently available in the training of the GPT model’s training dataset, thus introducing the challenge of ensuring the chatbot’s responses were accurate without hallucinations. I over- came this challenge by producing a controller that classified a user’s question on a series of pre-defined categories, provided a sequence of delimited data relevant to the category, and fed both the data and the prompt to the GPT model to answer the question. Given the inaccessibil- ity to a broader dataset of real customer queries, the chatbot struggled dealing with ambiguous queries, where the question asked by a user was not always clear. In my research I aim to ex- plore methodologies to enhance GPT models’ capabilities in processing and responding to ambiguous questions within a specific domain.

### PDF
[LGEN_Project_Proposal_ts3496.pdf](https://github.com/tmsavage/LGEN_Ambiguous_Queries/files/13274303/LGEN_Project_Proposal_ts3496.pdf)


## Project Midterm
### Description
First attempts to fine-tune BART-base model (and maybe BERT) on AmbigNQ dataset for ambiguous query rephrasing. Currently, the BART model is overfitting. Some techniques will need to be implemented, such as reducing the model's complexity, early stopping, batch normalization, and regularization techniques. I do also have access to a more complex (full) dataset. Moving forward for the final, I aim to implement these techniques to minimize overfitting. I will also encorporate the remaining experiments. 
### PDF
[TBD]

## Project Final
### Description
### PDF
[TBD]
