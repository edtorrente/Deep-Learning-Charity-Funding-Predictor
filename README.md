# Deep Learning Homework: Charity Funding Predictor

## Background

The non-profit foundation Alphabet Soup wants to create an algorithm to predict whether or not applicants for funding will be successful. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, you have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as the following:

* **EIN** and **NAME**—Identification columns
* **APPLICATION_TYPE**—Alphabet Soup application type
* **AFFILIATION**—Affiliated sector of industry
* **CLASSIFICATION**—Government organization classification
* **USE_CASE**—Use case for funding
* **ORGANIZATION**—Organization type
* **STATUS**—Active status
* **INCOME_AMT**—Income classification
* **SPECIAL_CONSIDERATIONS**—Special consideration for application
* **ASK_AMT**—Funding amount requested
* **IS_SUCCESSFUL**—Was the money used effectively

## Instructions

### Step 1: Preprocess the data

Using your knowledge of Pandas and the Scikit-Learn’s `StandardScaler()`, you’ll need to preprocess the dataset in order to compile, train, and evaluate the neural network model later in Step 2

Using the information we have provided in the starter code, follow the instructions to complete the preprocessing steps.

1. Read in the charity_data.csv to a Pandas DataFrame, and be sure to identify the following in your dataset:
  * What variable(s) are considered the target(s) for your model?
  * What variable(s) are considered the feature(s) for your model?
2. Drop the `EIN` and `NAME` columns.
3. Determine the number of unique values for each column.
4. For those columns that have more than 10 unique values, determine the number of data points for each unique value.
6. Use the number of data points for each unique value to pick a cutoff point to bin "rare" categorical variables together in a new value, `Other`, and then check if the binning was successful.
7. Use `pd.get_dummies()` to encode categorical variables

### Step 2: Compile, Train, and Evaluate the Model

Using your knowledge of TensorFlow, you’ll design a neural network, or deep learning model, to create a binary classification model that can predict if an Alphabet Soup–funded organization will be successful based on the features in the dataset. You’ll need to think about how many inputs there are before determining the number of neurons and layers in your model. Once you’ve completed that step, you’ll compile, train, and evaluate your binary classification model to calculate the model’s loss and accuracy.

1. Continue using the jupter notebook where you’ve already performed the preprocessing steps from Step 1.
2. Create a neural network model by assigning the number of input features and nodes for each layer using Tensorflow Keras.
3. Create the first hidden layer and choose an appropriate activation function.
4. If necessary, add a second hidden layer with an appropriate activation function.
5. Create an output layer with an appropriate activation function.
6. Check the structure of the model.
7. Compile and train the model.
8. Create a callback that saves the model's weights every 5 epochs.
9. Evaluate the model using the test data to determine the loss and accuracy.
10. Save and export your results to an HDF5 file, and name it `AlphabetSoupCharity.h5`.

### Step 3: Optimize the Model

Using your knowledge of TensorFlow, optimize your model in order to achieve a target predictive accuracy higher than 75%. If you can't achieve an accuracy higher than 75%, you'll need to make at least three attempts to do so.

Optimize your model in order to achieve a target predictive accuracy higher than 75% by using any or all of the following:

* Adjusting the input data to ensure that there are no variables or outliers that are causing confusion in the model, such as:
* Dropping more or fewer columns.
 ![columns](https://github.com/edtorrente/Deep-Learning-Charity-Funding-Predictor/blob/main/Images/columns.JPG)
* Adding more neurons to a hidden layer.
 ![neurons.jpg](https://github.com/edtorrente/Deep-Learning-Charity-Funding-Predictor/blob/main/Images/neurons.JPG)
* Adding more hidden layers.
 ![layers.jpg](https://github.com/edtorrente/Deep-Learning-Charity-Funding-Predictor/blob/main/Images/layers.JPG)
* Using different activation functions for the hidden layers.
 ![activation.jpg](https://github.com/edtorrente/Deep-Learning-Charity-Funding-Predictor/blob/main/Images/activation.JPG)
* Adding or reducing the number of epochs to the training regimen.
 ![epochs.jpg](https://github.com/edtorrente/Deep-Learning-Charity-Funding-Predictor/blob/main/Images/epochs.JPG)

**NOTE**: You will not lose points if your model does not achieve target performance, as long as you make three attempts at optimizing the model in your jupyter notebook.

1. Create a new Jupyter Notebook file and name it `AlphabetSoupCharity_Optimzation.ipynb`.
2. Import your dependencies, and read in the `charity_data.csv` to a Pandas DataFrame.
3. Preprocess the dataset like you did in Step 1, taking into account any modifications to optimize the model.
4. Design a neural network model, taking into account any modifications that will optimize the model to achieve higher than 75% accuracy.
5. Save and export your results to an HDF5 file, and name it `AlphabetSoupCharity_Optimization.h5`.

### Step 4: Write a Report on the Neural Network Model

For this part of the Challenge, you’ll write a report on the performance of the deep learning model you created for AlphabetSoup.

The report should contain the following:

1. **Overview** of the analysis: Explain the purpose of this analysis.

2. **Results**: Using bulleted lists and images to support your answers, address the following questions.

Initial Optimization Results:
![initial.jpg](https://github.com/edtorrente/Deep-Learning-Charity-Funding-Predictor/blob/main/Images/initial.JPG)
---
Attempt1: Dropping more columns:
![attempt1.jpg](https://github.com/edtorrente/Deep-Learning-Charity-Funding-Predictor/blob/main/Images/attempt1.JPG)
---
Attempt2: Add neurons to hidden layers and add more layers.:
![attempt2.jpg](https://github.com/edtorrente/Deep-Learning-Charity-Funding-Predictor/blob/main/Images/attempt2.JPG)
---
**Attempt3: Change activation layer at the output to "tanh".:**
![attempt3.jpg](https://github.com/edtorrente/Deep-Learning-Charity-Funding-Predictor/blob/main/Images/attempt3.JPG)


  * Data Preprocessing
    * What variable(s) are considered the target(s) for your model? 
	**IS_SUCCESSFUL**
    * What variable(s) are considered to be the features for your model?
	**APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT,**
	**SPECIAL_CONSIDERATIONS, ASK_AMT**
    * What variable(s) are neither targets nor features, and should be removed from the input data?
	**EIN, NAME**
  * Compiling, Training, and Evaluating the Model
    * How many neurons, layers, and activation functions did you select for your neural network model, and why?
	**NEURONS <= 100**
	**LAYERS = 3**
	**ACTIVIATION FUNCTIONS: RELU, SIGMOID, TANH**
    * Were you able to achieve the target model performance?
    ---
	**As indicated above, the process did NOT achieve the target=75% performance.**
    * What steps did you take to try and increase model performance?
	**Increase epochs**
	**Add more features to be dropped**
	**Change Activation functions**

3. **Summary**: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.

	**Deeep Neural Network is used for this classification model. The goal was to predict loan applicant success from charity_data.csv with 73% accuracy. This does NOT meet the 75% accuracy target.**

	**Since this is a classification problem, one can try Random Forest classifier. Also, this use case may beideal since this is a binary classification problem that can handle 2 hidden layers with less parameters to 
	optimize**

- - -

