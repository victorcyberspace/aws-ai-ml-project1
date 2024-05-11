
# <u>Report: Predict Bike Sharing Demand with AutoGluon Solution</u><br>
#### ASIIMWE VICTOR EMMANUEL

## <u>Initial Training</u>
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?

I encountered an error during the prediction phase --> KeyError: 2 required columns are absent from the dataset provided for transformation using AutoMLPipelineFeatureGenerator. Missing columns: ['casual', 'registered']. Consequently, I eliminated the mentioned columns from the training dataset, and the issue was resolved.

### What was the top ranked model that performed?

The top ranked model that performed was WeightedEnsemble_L3

## <u>Exploratory data analysis and feature creation</u>
### What did the exploratory analysis find and how did you add additional features?

The initial exploratory data analysis revealed negative values in both the train and test dataframes. Upon plotting the dataset features, I observed their distribution and structure. Certain features, like 'datetime,' were not informative. Therefore, breaking down the datetime into smaller units emerged as a potential solution to gain more insightful information. Subsequently, dividing it into smaller segments led to improved visualization, providing a clearer understanding of the date and time distribution of observations. 


### How much better did your model perform after adding additional features and why do you think that is?

The kaggle score improved slightly from 1.79917 (the score of the previous model) to 1.80003, indicating an enhancement in model performance. This improvement primarily stems from the feature engineering and data preprocessing steps. We derived more meaningful features from existing ones, such as extracting the month from the datetime feature. Additionally, categorical features underwent encoding to treat their values as categorical quantities rather than numeric ones.

## <u>Hyper parameter tuning</u>
### How much better did your model perform after trying different hyper parameters?

There was a significant decline in performance from a kaggle score of 1.80003 to a kaggle score of 1.42434

### If you were given more time with this dataset, where do you think you would spend more time?

I would spend more time on the AutoGluon hyperparameter optimization because it's a crucial aspect of model tuning that can significantly impact performance. With additional time, I would delve deeper into exploring different hyperparameter configurations, conducting more thorough grid or random search experiments, and possibly even exploring more advanced techniques like Bayesian optimization or evolutionary algorithms. Fine-tuning hyperparameters can often lead to substantial improvements in model accuracy and generalization, making it a worthwhile investment of time and effort. Additionally, I would also explore ensemble techniques within AutoGluon, such as model stacking or blending, to further boost predictive performance. Overall, dedicating more time to hyperparameter optimization would likely yield a more optimized and robust model for this dataset.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th></th>
      <th colspan="2" halign="left">hpo1</th>
      <th colspan="2" halign="left">hpo2</th>
      <th colspan="2" halign="left">hpo3</th>
    </tr>
    <tr>
      <th></th>
      <th></th>
      <th>GBM</th>
      <th>RF</th>
      <th>GBM</th>
      <th>RF</th>
      <th>GBM</th>
      <th>RF</th>
    </tr>
    <tr>
      <th>model or score</th>
      <th>params</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>initial</th>
      <th></th>
      <td>def</td>
      <td>def</td>
      <td>def</td>
      <td>def</td>
      <td>def</td>
      <td>def</td>
    </tr>
    <tr>
      <th>add_features</th>
      <th></th>
      <td>def</td>
      <td>def</td>
      <td>def</td>
      <td>def</td>
      <td>def</td>
      <td>def</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">hpo</th>
      <th>num_boost_round</th>
      <td>110</td>
      <td>-</td>
      <td>100</td>
      <td>-</td>
      <td>90</td>
      <td>-</td>
    </tr>
    <tr>
      <th>upper n_estimators</th>
      <td>-</td>
      <td>490</td>
      <td>-</td>
      <td>480</td>
      <td>-</td>
      <td>470</td>
    </tr>
    <tr>
      <th>kaggle</th>
      <th></th>
      <td>1.42554</td>
      <td></td>
      <td>1.42477</td>
      <td></td>
      <td>1.42495</td>
      <td></td>
    </tr>
  </tbody>
</table>
</div>

def - default values, GMB - Gradient Boosting Machine, RF - Random Forest 

### Create a line plot showing the top model score for the three (or more) training runs during the project.

![image.png](attachment:image.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

![image.png](attachment:image.png)

### <u>Summary</u>

In this project, we learned about the impressive idea of AutoML, which is encapsulated in the AutoGluon library. We also gained experience in exploratory data analysis (EDA) and feature engineering with our dataset. Through these preprocessing and exploration steps, we recognized the importance of data quality, which can often yield better results than model quality alone. This concept aligns with a research interest in the AI and ML community known as Data-Centric AI (DCAI). DCAI emphasizes prioritizing data quality over model quality, a focus that some researchers find intriguing.
