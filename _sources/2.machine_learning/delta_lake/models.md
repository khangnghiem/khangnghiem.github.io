# Models

## Null Values

Most machine learning libraries give an error if you try to build a model using data with missing values.

### Three approaches

#### 1) A Simple Option: Drop Columns with Missing Values

The simplest option is to drop columns with missing values.

Unless most values in the dropped columns are missing, the model loses access to a lot of (potentially useful!) information with this approach.

#### 2) A Better Option: Imputation

Imputation fills in the missing values with some number. For instance, we can fill in the mean value along each column.

The imputed value won't be exactly right in most cases, but it usually leads to more accurate models than you would get from dropping the column entirely.

![alt text](images/models-1.png)

#### 3) An Extension To Imputation

Imputation is the standard approach, and it usually works well. However, imputed values may be systematically above or below their actual values (which weren't collected in the dataset). Or rows with missing values may be unique in some other way. In that case, your model would make better predictions by considering which values were originally missing.

In this approach, we impute the missing values, as before. And, additionally, for each column with missing entries in the original dataset, we add a new column that shows the location of the imputed entries.

In some cases, this will meaningfully improve results. In other cases, it doesn't help at all.

![alt text](images/models.png)
