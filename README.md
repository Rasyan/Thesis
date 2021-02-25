This github repository contains the code for the unpublished master Thesis by Rasyan Ahmed called: Modeling EEG responses to narrative speech

The code has been build with ease of use in mind. There are three main notebook files which are all commented.
  - Calculate_surprise.ipynb: contains the code for calculating how surprising words are, The broderick method and our own
    - Commands for recreating all variants discussed in the Thesis are provided at the end of the file.
    - Inputs: Word order information. (provided in repo in the stimuli/Text folder) The Word2Vec vectors of each word (necessary subset of the vectors provided in repo as limited_vectors.txt), and the full text spoken in the audio book (provided in repo as full_text.txt)
    - Outputs: Surprisal values saved in the numpy file format in the vectors folder.  (The results for all variants are provided in repo)
  - Train.ipynb: Contains the code for creating the surprisal vectors form the surprisal values, preprocessing the EEG, and calculating the TRF.
    - Commands for recreating most variants discussed in the Thesis are provided at the end of the file.
    - Inputs: The previously calculated surprisal values in the vectors subfolder, and the EEG files located in the EEG folder.
    - The EEG files are not provided in the repository due to file size limitations. They need to be downloaded from https://datadryad.org/stash/dataset/doi:10.5061/dryad.070jc and inserted into the EEG folder.
    - Outputs: The weights of the TRF model stored in results/coefs and the R2 of the models stored in results/scores. (Due to file size limitations the repo only provides the results for the broderick model, the best performing bert model and the static model. The others need to be generated in Train.ipynb)
  - Visualize.ipynb: Contains example code of how to create graphs and charts to visualize the results from the Train.ipynb notebook.
    - You select the models to visualize at the start, the graphs automatically add all selected models.
    
The code has been confirmed to run at these specific versions of the following libraries: 
  - pytorch_pretrained_bert: 0.6.2
  - mne: 0.20.7
  - Torch: 0.4.1
  
We can not guarantee compatibility with newer or older versions.
