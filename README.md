# Cough-Sensing


Important files and Directories

- data/   - Find the data in this [drive](https://drive.google.com/drive/folders/1859z4bq1dD8xsEv7DfdmlQPY7K_Nag0S?usp=sharing)

- Playground.ipynb          - (Experimental)
- bee-not-to-bee.ipynb      - cleaning the data for Bee-not-to-bee dataset (Binary classifier for transfer learning)
- ESC.ipynb                 - cleaning the data of ESC dataset from Kaggle - for transfer learning


# Training on Free Sound dataset
### Here every notebook presents a different model architecture
### They are also save dwith tehg similar names

The data used for the training below is in "data/freesound-audio-tagging" directory 

- 1) Freesound - 1D CNN.ipynb                   - Base 1D CNN model - 0.5 sec input - 22050 values at 44100Hz
- 2) Freesound-1D CNN GlobalPool.ipynb          - Chnaging last layer of base model to globapool - 0.5 sec input - 22050 values @ 44100Hz
- 3) Freesound-GlobalPool-44100.ipynb           - same as 2) except changed the imput length to 1 second - 44100 Values @ 44100Hz
- 4) Freesound-GlobalPool-8CH.ipynb             - based on 2) chnage dthe input to 8 channels using band pass filters
- 5) Freesound-GlobalPool-Deep.ipynb            - based on 2) but added few layers to make network deeper
- 6) Freesound-GlobalPool-Deep-BatchNorm.ipynb  - based on 5) added batchnorm after every 1D CNN to aid the deeper networks


# Transfer Learning
### I have selected "FreeSound_1D_conv_global_pool_deep_batchnorm_2400_epoch.stDict" from model weights folder with architecture of 6) for the transfer learning

The data used for this training is augmented from "data\collected" directory - although after training the augmentation is not required

- Final Cough Model - Requires 0.5 sec input 22050 values @ 44100Hz returns 2 classes Cough or not - tested accuracy - 95%



All the required libraries are in requirement.txt file 

in addition
You need

[PyTorch](https://pytorch.org/get-started/locally/)
[Label-studio](https://github.com/heartexlabs/label-studio)


