******************************************************************
GitLab repository associated with the paper Beat It!
All code written by Matthew Dwyer 05/05/2021
******************************************************************


This notebook was designed to be used with Google Colab. To use this notebook with Colab, simply open the notebook in Colab and when mounting the Google Drive in code block two, follow the link and click "Use another account" and sign in with the credentials,

email: beat.it.fyp@gmail.com

password: FYP_BeatIt!123

If this notebook is not being used with Colab, the BPMs and wavs folders can be accessed here,

BPMs: https://drive.google.com/drive/folders/1DlHw4-HaL8bzKHRxMwxb5cVYh4TEABem?usp=sharing

wavs: https://drive.google.com/drive/folders/12vr7NvFCweC2w9xg3rb9_h9OzFPZzpE7?usp=sharing

When using this notebook outside of Google Colab, some slight changes to the directories variables might have to be changed to suit the file structure where the notebook is stored. The intended file structure is indicated in this repository, starting with the "data" folder.

To use this notebook, just click through and run each block sequentially.

The buildData function takes 3 arguments, the number of samples (a variable that is used during mel-spectrogram) computation, the length of the slices created, and a flag indicating if the data needs to be rebuilt or not. This function returns the data that has been transformed into mel-spectrograms, sliced along the time axis creating half overlapping windows, and split into training, validation, and testing sets. 

After this function declaration the network is defined along with the inception block function. The network can be altered by taking out however many inception blocks are necessary along with the average pooling and batch normalization layers that precede it.

After this the accuracy1 score function is defined and the buildData function is called. The code block after this compiles the optimizer, loss function, accuracy scores, and callbacks. Again, the directory for the early stopping save location may have be altered to fit the directories you are running on.

After this the network is trained using the parameters, callbacks, and data defined in the previous blocks. What follows are three blocks used to create graphs to visualise the training and validation loss, accuracy0 score and accuracy1 score. The final block loads the model weights with the lowest validation loss and tests it on the testing dataset.
