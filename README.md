# VocalRemoverSurvey

This project is a comparative survey of various deep learning models used for signal source seperation of music.
These models seperate a mp4 or wav file into four different stems, the vocals, the drums, the bass, and the instrustments.

## Models
We compared six models and one baseline model with four different metrics and a qualative evalaution. four of the models are
research models and two of the models are industry models.
Thee models are the Following
- HT Demucs from Facebook Research (Research Model) https://github.com/facebookresearch/demucs
- Spleeter from Deexer (Research Model) https://github.com/deezer/spleeter
- Open Unmix from SigSep (Research Model) https://github.com/sigsep/open-unmix-pytorch
- Ultimate Vocal Remover (industry model) https://ultimatevocalremover.com
- VocalRemover.org (Industry Model) https://vocalremover.org
- MDX net (Research Model) https://github.com/kuielab/mdx-net
- Baseline Model made by our team

These models varied in architecture from using U-nets, Transformers, and RNN architecture.

## Dataset
The dataset used for this project is the MUSDB18 dataset provided by SigSep (https://sigsep.github.io/datasets/musdb.html).
This dataset is comprised of 150 songs from a variety of artists and genres, 100 of these songs belong to the training dataset
and the remaining 50 in the test dataset.

## Evaluation
After running the models to get the seperated vocals of each song in the test dataset, we used the museval python package to 
evaluate the models. The Museval package evluates stems on four metrics:
- Signal Distortion Ratio (SDR)
- Signal to Artifact Ratio (SAR)
- Signal Interference Ration (SIR)
- Image to Spatial Ratio (ISR)

## Results

###Averages controlling for outliers with a trimmed mean
|Model|SDR|SAR|ISR|SIR|
|---|---|---|---|---|
|Baseline|-2.831|9.866|-0.988|-5.612|
|HT-Demucs| -3.052|-9.205|-0.572|23.593|
|Spleeter| 6.006| 5.535| 13.080| 23.097|
|MDX-Net| 9.084|9.049|17.97|25.153|
|Open-Unmix|7.087|8.293|14.42|11.551|
|Ultimate Vocal Remover| 8.515|8.806|17.441|24.792|
|Vocal Remover|8.395|8.11|14.729|27.026|

### Variance
|Model|SDR|SAR|ISR|SIR|
|---|---|---|---|---|
|Baseline|22.254|5.016|1.354|92.576|
|HT-Demucs| 40.252|15.263|0.254|67.479|
|Spleeter|40.252|12.49|28.21|83.575|
|MDX-Net|54.325|16.871|30.369|128.292|
|Open-Unmix|11.342|18.015|32.509|52.577|
|Ultimate Vocal Remover|48.695|20.14|30.367|121.769|
|Vocal Remover|18.51|10.878|24.593|73.736|

## Files
- MDX-net directory: this is the code to run the MDX-Net model, here is the github repo with more information on how to run this model (https://github.com/kuielab/mdx-net)
- Ultimate Vocal Remover is application that must be installed on your computer from the link mentioned above, you input the files you want to seperate and it outputs the stems you request
- Vocal Remover, to run this model go to Vocalremover.org and upload the input files and it will download the outputs for you.
- The .ipynb files that run models are for open unmix, ht-demucs, and spleeter. you mount the notebook to your google drive and specify which folders the data is coming from and where it is being output.
- the evaluation notebooks operate the same was as the model notebooks, you specify the google drive folder with the inputs and the musdb18 dataset as well as the file types and it will run the evaluation

## More information
here is the link to our final presentation if you would like to see more information:
https://docs.google.com/presentation/d/1ovE5-4vGLjDtA6TcDmyPR6Qjr34_hd3upGMxGBXhlWI/edit#slide=id.g2d05083ae11_0_35

