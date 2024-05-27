This project involves training a Transformer model to generate poetry. The steps can be summarized as follows:
Data Preparation
1.	Download and Extract Dataset:
•	Use gdown to download a ZIP file containing the dataset.
•	Unzip the downloaded file to access poem_final.csv.
2.	Read and Clean Data:
•	Load the dataset into a Pandas DataFrame.
•	Normalize the text by stripping whitespace from the start and end of each poem.
3.	Tokenization and Vocabulary Building:
•	Define a simple tokenizer that splits text by spaces.
•	Define a function to yield tokens from the DataFrame.
•	Build a vocabulary from the tokens, including special tokens such as <unk>, <pad>, <sos>, <eos>, and <eol>.
•	Set default index for unknown tokens and identify indices for special tokens.
4.	Vectorization and Padding:
•	Define functions to vectorize text (convert tokens to indices) and to pad/truncate sequences to a fixed length.
Dataset Creation
5.	Poem Dataset Class:
•	Create a custom PoemDataset class that:
	Splits each poem into quatrains (4-line stanzas).
	Prepares input and target sequences with padding masks.
	Converts sequences into tensors for model input.
6.	Data Loader:
•	Initialize a DataLoader to handle batch processing of the dataset.
Model Definition
7.	Positional Encoding:
•	Implement a positional encoding module to add position information to token embeddings.
8.	Transformer Model:
•	Define a Transformer-based model that:
	Embeds input tokens.
	Adds positional encodings.
	Passes the encoded inputs through multiple layers of a Transformer encoder.
	Projects the outputs to vocabulary size using a linear layer.
Training
9.	Training Loop:
•	Define training parameters (learning rate, number of epochs).
•	Use cross-entropy loss and stochastic gradient descent for optimization.
•	Implement a learning rate scheduler to decay the learning rate.
•	Train the model, iterating through the DataLoader, computing loss, performing backpropagation, and updating weights.
Inference
10.	Text Generation:
•	Define a sampling function to sample next tokens based on output logits and a temperature parameter.
•	Generate new text by feeding an initial input to the model and sampling subsequent tokens iteratively until the end of sequence token is generated or a maximum length is reached.
•	Decode the generated token indices back to text and format the output.
Code Summary
The project integrates various components:
•	Data Preparation: Reading, normalizing, tokenizing, and vectorizing the dataset.
•	Dataset Handling: Creating a custom dataset class for managing input sequences and padding.
•	Model Definition: Implementing a Transformer model with positional encoding.
•	Training: Implementing a training loop to optimize the model.
•	Inference: Generating new poems using the trained model and sampling technique.

