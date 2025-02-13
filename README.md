# Ndwom: A Multimodal Music Information Retrieval Dataset for Akan Musical Videos

GitHub: [https://github.com/CAIRGH/Multimodal-Twi-Music](https://github.com/CAIRGH/Multimodal-Twi-Music)

Research Square: [https://www.researchsquare.com/article/rs-5876078/v1](https://doi.org/10.21203/rs.3.rs-5876078/v1)

## About Dataset
This dataset is a curation of music videos from 6 different genres of the Akan Twi language namely, 
Gospel, Highlife, HipHop, Love Poem, Rap and Soul. This Akan MIR music video dataset comprises of the different
modalities, textual, visual and audio used for MIR applications such as music sentiment anal-
ysis, genre classification, emotion recognition and recommender systems. The curation of this
datasets includes selecting music videos in different genres that reflect the diverse culture and
language of the Akans, downloading them to extract the different modalities for MIR tasks.
Python scripts were written to extract these relevant modalities. This GitHub repository contains two main folders
the Dataset folder and the notebooks folder. The Dataset folder contains the textual modalities for the different music videos.
Due to copyright restrictions, the music video and audio files as well as the different segmentations 
have not been provided. However, the data can be reproduced using the Python programs found in the Notebooks 
folder. 

### Dataset Folder
The Dataset folder contains the CSV files for each of the six (6) genres. 
Found in each genre subfolder are the following files.
1. [Genre] VideoSegments: [Genre] is the name of the genre of the music. This file contains
the number of segments of video clips for that particular genre. The number of segments depends on the
size of the music video. Information on the different columns and metadata found in them
can be found in the research paper above. 

2. [Genre] AudioSegments.csv: Just as in the [Genre] VideoSegments.csv, this file has the list
of the different segments of the audio clips of the music videos. The metadata of the AudioSegments are the same as the VideoSegments
with the values changing in some columns such as the Filename where the file ends in .mp3
instead of .mp4 as found in the VideoSegments and the type of the file being MP3 instead
of MP4 in the [Genre] VideoSegments.csv file. The data is mostly the same except for few
differences as stated above.

3. [Genre] Compete Audial Features.csv: This file shows the acoustic features of the different segments of the audio clips, it has the same
metadata as the video and audio segments with the addition of the following acoustic fea-
tures; Onset Strength, Chroma Short Time Fourier Transform (STFT), Harmonic Percussive
Source Separation (HPSS), Zero Crossing Rate, and the Mel-Frequency Cepstral Coefficients
(MFCC) which can be used for machine learning tasks. 

4. [Genre] VideoImages.csv: Just as each video is made up of a series of frames or images coming
together, each segment of the music video and consequently the music video itself is made up
of images. This file contains the different frames of the segments of the video files. However,
due to the size of the video files only a subset of the segments were used for extraction of the
frames. These frames can also be used for maching learning tasks providing a holistic dataset for the 
machine learning tasks. 

Please note that some of the files csv files have the same files in other extensions. This was to enable
viewing on Google Drive when working on the dataset since the work was mainly done using Google Drive and Google Colab.

### Notebooks Folder
Jupyter Notebook was used to generate the different dataset files found in the Dataset folder and
this folder contains the python code for this automation. The different Python scripts are:
1. download songs.ipynb: This script is used to download the videos from YouTube using the
URL as found in the CSV files.
2. split music videos.ipynb: The Jupyter notebook here splits the 180 video files into smaller 15
second chunks of segments. The splitting is done based on the length of the video clip. This
greatly reduces the size of the files and significantly betters the performance during model
training and evaluation of machine learning models.
3. separate audio video.ipynb: This Python script separates the audio modalities of each of the
video chunck/segment from the video clip.
4. extract features.ipynb: The Python script used to obtain the different spectral-based acoustic
features from each segmented audio clip is ontained in this Jupyter notebook.
5. extract video images.ipynb: This Jupyter notebook contains the Python program used to
generate the frames/images of the different segments of the music videos.
6. generate graphs.ipynb: This Jupyter notebook contains the Python program used to generate
the graphs/distribution of the different segments of the music videos based on genre, language
and sentiment polarity.

## Authors
* Dr. Stephen E. Moore 
* Nana Akwasi Asare
* Samuel Kwadwo Kubiti
