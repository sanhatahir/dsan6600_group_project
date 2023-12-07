# Deforestation in Bolivia: an image segmentation approach
### DSAN6600 group project
### Sanha Tahir, Sukriti Mahajan, Fanni Varhelyi

This repository contains an analysis on satellite images to estimate the rate of deforestation in a given area in Bolivia between 2017 and 2023. The analysis utilizes U-Net and image segmentation, and works with satellite images sourced from Planet.

The trained model can be accessed in the model folder and is usable for any other time period or Amazonian rainforest area. 

### Data

To acquire new test images from Planet, you can create an account here and use your API Token with the provided data collection notebook to download a new set of images: https://www.planet.com/nicfi/ 

The training datasets were aquired from:

Amazon 1 (3-band rgb images, 30 + 15) -- https://zenodo.org/record/3233081

Amazon 2 (4-band images, 499 + 100) -- https://zenodo.org/record/4498086#.YMh3GfKSmCU

Atlantic (4-band images, 485 + 100) -- https://zenodo.org/record/4498086#.YMh3GfKSmCU


Our test data of Bolivia was acquired from the publicly available Planet API -- https://developers.planet.com/docs/apis/


### Files

/src
1. Data collection
   A script that contains funstions to download lists of quads per multiple mosaics (satellite images per time periods) from the Planet Basemaps API.
2. UNet_Amazon
   A script for training the final model on Amazon 2 data
3. Results
   A script analyzing the results of the model focusing on a small area in Bolivia. Calculates and compares forests in a given area across multiple time periods.

/exploration
1. Semantic segmentation
   A base model used as initial reference to compare the U-Net with
2. UNet_Amazon_bolivia
   An initial model run on 30 training and 15 validation images
3. data_augmentation
   An initial experiment with data augmentation

/model
1. Running_models.ipynb:
   * Loads and ingests data 
   * Runs and saves all 8 models
   * Test models on unseen Bolivia images 
   * Get evaluation metrics 
2. predicting_across_bolivia.ipynb:
   * Loads model_unet (the best performing model from our experiments)
   * Loads and processes our untested dataset of Bolivia 
   * Runs prediction for masks on these images and calculates required metrics 

/ Archive:
1. UNet_01: First run of U-Net Architecture from given site:
  https://www.kaggle.com/code/vanvalkenberg/image-segmentation-u-net-for-self-driving-cars/notebook?scriptVersionId=54705605 


To be moved: 
PROMISING: 
1. UNet_Amazon_bolivia -> exploration
2. Data augmentation -> exploration
3. 