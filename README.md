# deep-learning-challenge

# Report on the Neural Network Model:

## Overview of the analysis: 
The objective of this analysis was to develop a neural network model capable of selecting applicants for funding who are most likely to succeed in their endeavors. The primary focus was on optimizing the model to enhance its ability to accurately predict whether an application would be successful, based on the available data. Several attempts were made to improve the model’s performance by adjusting its structure, modifying training settings, and refining data preprocessing techniques to achieve optimal results.

## Results:

### Data Preprocessing

#### Target Variable:
The target variable for this model was the "IS_SUCCESSFUL" column, which indicated the outcome of each funding application.

Feature Variables:
The features used for building the model included several metadata columns that described the organizations, such as:

- EIN
- NAME
- APPLICATION_TYPE
- AFFILIATION
- CLASSIFICATION
- USE_CASE
- ORGANIZATION
- STATUS
- INCOME_AMT
- SPECIAL_CONSIDERATIONS
- ASK_AMT

Variables Removed:
Both the EIN and NAME columns were removed initially as they were deemed not directly relevant to the model’s predictions. However, in the final iteration, the NAME column was reintroduced and used in training the model.

## Compiling, Training, and Evaluating the Model

### Original Model:
- Architecture: 2 hidden layers and 1 output layer
- Training: 50 epochs
- Performance:
      - Accuracy: 0.7296
      - Loss: 0.5582
- Evaluation: The initial model achieved an accuracy of 0.7296 with a loss of 0.5582. Although this was a reasonable result, further tuning and optimization were needed to improve accuracy.

### Attempt 1:
- Changes: Increased the number of epochs from 50 to 100, while keeping the network architecture unchanged.
- Performance:
      - Accuracy: 0.7293
      - Loss: 0.5643
- Evaluation: Despite increasing the training time, the model’s accuracy slightly decreased to 0.7293, and the loss rose to 0.5643. This suggested that simply extending training time without further modifications could lead to overfitting.

### Attempt 2:
- Changes: Increased the complexity of the model by adding more hidden layers (total of 4 hidden layers) and increased the training to 100 epochs.
- Performance:
      - Accuracy: 0.7303
      - Loss: 0.5873
- Evaluation: Adding more layers and extending the training resulted in a marginal improvement in accuracy to 0.7303, but with a higher loss of 0.5873, indicating that the model might be overcomplicating the relationships in the data.

### Attempt 3:
- Changes: Used the Keras Tuner to automate the selection of the best model architecture.
- Performance:
      - Accuracy: 0.7340
      - Loss: 0.5572
- Evaluation: The Keras Tuner helped achieve an accuracy of 0.7340 and a slightly lower loss of 0.5572, demonstrating that automated hyperparameter tuning was more effective than manual adjustments.

### Fourth and Final Attempt:
- Changes: The NAME column was reintroduced, and input data was adjusted to remove outliers. The model returned to the original architecture (2 hidden layers, 1 output layer) and trained for 50 epochs.
- Performance:
      - Accuracy: 0.7876
      - Loss: 0.4623
- Evaluation: This attempt resulted in a significant improvement, with an accuracy of 0.7876 and a lower loss of 0.4623. This suggests that reintroducing the NAME column and refining the input data were crucial to achieving better performance.

## Were you able to achieve the target model performance?

Yes, after several adjustments to both the input data and model architecture, the target model performance was met. The final model, with the original architecture of 2 hidden layers and 1 output layer, trained for 50 epochs, achieved the desired accuracy.

## What steps did you take in your attempts to increase model performance?

- Extended Training: 

The number of epochs was increased to provide the model more time to learn from the data, but this led to signs of overfitting without substantial gains in accuracy.

- Architectural Changes: 

Additional hidden layers were introduced to increase the model’s complexity, but this resulted in minimal improvements, showing that deeper networks didn’t necessarily perform better for this dataset.

- Keras Tuner:

Automated hyperparameter tuning with Keras Tuner was employed to optimize the model’s architecture, leading to some improvement in accuracy and a slight reduction in loss.

- Data Re-Evaluation: 

The input data was revisited, with the NAME column being added back, and outliers were removed. These adjustments played a crucial role in achieving the highest accuracy.

## Summary:

Through multiple optimization attempts, it became clear that carefully adjusting the model’s architecture and refining the input data were critical to achieving optimal performance. The final model’s accuracy improved from 0.7296 to 0.7876 by using a combination of input data modifications and model tuning techniques.

## Recommendation:

To further enhance model performance, re-running the Keras Tuner with more refined data preprocessing could yield additional gains. Additionally, exploring other machine learning models, such as Random Forests or Gradient Boosting, may prove beneficial in finding a model that better fits the characteristics of the dataset.

**Reference:**
- Data for this dataset was generated by edX Boot Camps LLC, and is intended for educational purposes only.
- IRS. Tax Exempt Organization Search Bulk Data Downloads. (https://www.irs.gov/charities-non-profits/tax-exempt-organization-search-bulk-data-downloads)
- Chatgpt used to improve logic, error correction and generate sections of code and improve reporting of analysis.
- Google to get syntax for adapting to my code.
