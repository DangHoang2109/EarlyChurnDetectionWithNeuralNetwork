# EarlyChurn-Base: User Churn Prediction for Mobile Games

## What's This About?
This repository contains the dataset used in our research paper focused on predicting user churn in the mobile game "8Pool Offline" developed by Cosina Studio. The dataset is collected from July 4 to July 30, 2023.

## Table of Contents
1. [What's This About?](#whats-this-about)
2. [How to Use](#how-to-use)
   - [Requirements](#requirements)
   - [Instructions](#instructions)
3. [About the Data](#about-the-data)
   - [Cleaned Data](#cleaned-data)
   - [Data for Modeling](#data-for-modeling)
4. [Citing Us](#citing-us)
5. [License](#license)
6. [Contact](#contact)

## How to Use

### Requirements
- Python 3.x
- Pandas library
- A CSV reader

### Instructions
1. Move the Google Drive Storage which contain the dataset: [Drive Storage](https://drive.google.com/drive/folders/1dCqZyXeC4K-GGyaL-kpJ07CDgDGmniKA?usp=sharing)
2. Navigate to the data folders to access the cleaned and preprocessed data.

## About the Data

### Cleaned Data
The `CleanedDataset` folder contains a `.csv` file with extracted data from Cosina Studio's logging system and BigQuery nested data format. This data is not yet processed for research analysis.

### Data for Modeling
The `TrainDataset` folder contains six `.csv` files:
- Training data (`X_train.csv` and `y_train.csv`)
- Testing data (`X_test.csv` and `y_test.csv`)
- Validation data (`X_val.csv` and `y_val.csv`)

These sets are fully prepared for model training and testing, with an 848,145-user dataset split into 98% for training, 1.5% for testing, and 0.5% for validation, undergone the preprocessed steps mentioned on related paper.

### Data Preprocessing Summary

- **Initial Cleaning**: Removed empty records and extreme values.
- **UserChurned Label**: Identified based on user activity in following days.
- **High Cardinality**: Simplified 'Mobile Brand' and 'OS Version' to top 8 and top 10 most common values, respectively.
- **Tutorial Step Outliers**: Removed values that are more than 10 times the average.
  
### Feature Selection

Given the aim of creating a model that is generalizable across various types of mobile games, the dataset includes features that are universally applicable. Specifically, the features are categorized into two main types: device information and time spent in mandatory tutorial steps.

| Feature Name             | Description   |
|--------------------------|---------------|
| Category                 | The category of the device used (mobile, tablet, etc.) |
| Mobile brand name        | The brand name of the mobile device |
| Operating system version | The version of the operating system on the user's device |
| Tutorial step _*         | Time spent in specific tutorial steps in seconds. These are unique to the 8Pool game and are mandatory steps that guide the user on how to play the game and understand its core loop |
| UserChurned              | A binary value indicating whether the user churned (True) or not (False) |


## Final Dataset

- **Balanced**: 53.6% likely to churn (Class 1) and 46.4% likely to stay (Class 0).
- **Extendable**: Easy to add more data or adapt for other games.

## Citing Us
If you use this dataset for your own research, please refer to our original paper for methodology and cite us accordingly.

## License
This project is licensed under the MIT License. For more details, see the [LICENSE.md](LICENSE.md) file.

## Contact
- HoangHaDang: hoanghd.17@grad.uit.edu.vn
- CamNguyenTan: camnt@uit.edu.vn
