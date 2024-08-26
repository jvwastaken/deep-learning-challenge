## Neural Network Report

1. **Overview:**
    - The purpose of this analysis is to report on the performance of the deep learning model for the Alphabet Soup.

2. **Results:**
    - Data Processing:
        - The target would be whether or not the application type was successful: `application_df_encoded['IS_SUCCESSFUL']`.
        - The features would be the rest of the columns excluding the `IS_SUCCESSFUL` column.
        - The two columns `EIN` and `NAME` of the dataframe should be removed because they are neither target nor features.
    - Compiling, Training, and Evaluating the Model:
        - These are the parameters for my neural network model:
            - Total neurons: 300
            - Total layers: 6
            - Total functions used: 3
        - The reason why I used the above quantities of parameters is because I also tried to find the best hyperparameters using *keras_tuner*. I based my neural network off of what *keras_tuner* provided.
        - I was not able to achieve the target model performance of 75% or higher.
        - The following were methods I have tried in order to increase the model's performance:
            - Changing the binning quantities for `APPLICATION_TYPE` and `CLASSIFICATION`.
            - Dropping non-beneficial ID columns, i.e. `EIN`, `NAME`. I've also tried dropping: `STATUS`, `SPECIAL_CONSIDERATIONS`, `AFFILIATION`, and `USE_CASE`.
            - Increasing/decreasing the number of neurons per hidden layer.
            - Changing the activation function for each layer.

3. Overall, the model's accuracy averaged around 72-74% even with optimization. Even with using `keras_tuner` to find the best hyperparameters, the top 3 models all had an accuracy of 73%. A different model that I would suggest is a supervised learning model algorithm that can handle a dataset with many features such as Alphabet Soup, namely, algorithms like Random Forest or perhaps Naive Bayes. The 2 aforementioned algorithms can handle data that is too large.