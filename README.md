# tv-scriptgen
Running Floyd-Hub:

Install
# python2
	$ pip install -U floyd-cli
# python3
	$ pip3 install -U floyd-cli
# anaconda python3
	$ source activate env-name && pip3 install -U floyd-cli
LogIn
	$ floyd login
Setup
	$ floyd init dlnd-tv-script-generation 
Running
	$ floyd run --cpu --mode jupyter --env tensorflow
	$ floyd run --gpu --mode jupyter --env tensorflow
  
  
# Project Information
The function create_lookup_tables create two dictionaries: vocab_to_int and int_to_vocab
The function token_lookup returns a dict that can correctly tokenizes the provided symbols.
Implemented the get_inputs function to create TF Placeholders for the Neural Network with Input, Target and Learning Rate placeholders.
Enough epochs to get near a minimum in the training loss, no real upper limit on this. Just need to make sure the training loss is low and not improving much with more training.
Batch size is large enough to train efficiently, but small enough to fit the data in memory. No real “best” value here, depends on GPU memory usually.
Size of the RNN cells (number of units in the hidden layers) is large enough to fit the data well. Again, no real “best” value.
The sequence length (seq_length) here should be about the size of the length of sentences you want to generate. Should match the structure of the data.
