Slides available: [here](https://docs.google.com/spreadsheets/d/1sJXd1Vkvk-YXXPUDlzlFLwRVaqmBrpAi9uwmjHtGI1I/edit#gid=0)

Project 1: Introduction to NLP and AllenNLP

Project 2: Group Project: 'Mitigating Gender Bias in Text Classification using a Graph Convolutional Network'
[Medium Article](https://towardsdatascience.com/mitigating-gender-bias-in-occupation-classification-805edb389729?source=friends_link&sk=3966a9c714ffaee7dbc642075d8a18b8)
______________

### Mitigating gender bias in occupation classification of job biographies with graph convolutional network
We use adapt the TextGCN by Yao et al. (2018) https://github.com/yao8839836/text_gcn to classify job biographies from the https://github.com/Microsoft/biosbias dataset. We investigate the mitigation of gender bias by comparing the predictions of our trained model for the original test dataset and for a transformation of our test dataset where explicit gender indicators are removed or "scrubbed" in line with De-Arteaga et al. (2019).

Download data at https://drive.google.com/drive/folders/1h2oILArbrTsdN5VrdhWAKpzppwOXtyZO?usp=sharing .

Note that this is only a demo and does not include the training of our TextGCN or the predictions for the "scrubbed" test dataset.

Also, note that we ran into problems when running the demo locally using Jupyer notebooks due to conflicting packages. We had more success running on Google colab and mounting the Google drive to access our data. We have included the Google drive mounted version of the demo in the Google drive folder above so it can be run directly in colab.

    1. Imports
        import packages
    2. Data
        define directory path
        read raw data csv files into pandas for both original and reduced datasets from directory
        create summary statistic table with length of training and test sets and number of occupation labels
        create occupation frequency chart for original data set
    4. Utility Functions
        define some utility functions
    5. Graphs
        clean original test dataset by removing words that are not included in the training vocabulary
        build feature vectors and one hot labels for original test data
        load feature vectors, one hot labels and adjacency matrix for original training data from directory
    6. Model
        define initialisation functions
        define layers
        define training metrics
        define model
    7. Prediction
        load GCN trained with original dataset with gender indicators
        predict occupation labels for original dataset
    8. Analyses
        calculate TPR, TPR gender gap  for the gender "female"
        plot and compute correlation
        compute gender imbalance and compounding factor
        load predictions on scrubbed test dataset
        TPR, TPR gender gap and correlation between TPR gender gap and on scrubbed dataset
        plot for original compared to scrubbed test dataset
        proportion of compounding factors pulled towards 1 after scrubbing
