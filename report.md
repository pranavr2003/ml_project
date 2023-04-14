<h2 style="text-align: center;"> Machine Learning </h2>
<h3 style="text-align: center;"> Course Project Report </h3>
<h4 style="text-align: center;"> (Draft - 01, Team No: 01) </h4>

<style>
    .center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 50%;
}
</style>

---------------------------------------------------------------

#### Title of the project: Superconductivity Data
    
<br>
    
__Student 1__: Sarang Galada, sarang.g-25@scds.saiuniversity.edu.in   
__Student 2__: R Sai Pranav Aadhitya, saipranavaadhitya.r-25@scds.saiuniversity.edu.in
    
<br>
    
#### ML Category: Regression

---------------------------------------------------------------    
<br>

__1. Introduction__  

- <u>Problem Statement</u>: Superconductivity is the property of certain materials to exhibit zero electrical resistance, ie. ability to conduct direct current electricity without energy loss, when cooled below their critical temperature. Due to its unique advantages, a lot of research has been directed towards superconductivity and its applications. Despite that, the relationship between Critical Temperature (below which the material behaves as a superconductor) and the material’s chemical properties is poorly understood. This has propelled efforts to use Machine Learning techniques to model critical temperature and understand its relationship with the material’s chemical properties.

<br>

__2. Dataset and Features__

- <u>Details of the dataset</u>: This project makes use of the Superconductivity dataset from University of California, Irvine’s Machine Learning Repository, sourced from Dr. Kam Hamidieh. The dataset consists of 21,263 rows and 82 columns. The rows represent different superconductor compounds (for eg. La<sub>2</sub>CuO<sub>4</sub>), while the columns depict various statistical measures of their chemical properties (for eg. mean Atomic Mass, standard deviation of Thermal Conductivity, range of Heat of Fusion and so on). Of these 82 columns, 81 are the input features for our learning model, with the 82nd column (Critical Temperature) being the target variable we wish to predict. 

- <u>Exploratory Data Analysis</u>: As mentioned earlier, the dataset contains 21,263 rows and 82 columns. 

<br>

![data.head()](img/data_head.jpeg "Peek into the first 5 rows of the dataset")  

<br>

>> Majority of the columns are of type float64, with the exception of two (`number_of_elements`, `range_Valence`), which are of type int64 and hence take discrete values. The dataset doesn’t contain any missing values, although it was found to contain 66 duplicate rows, which had to be dropped as part of data cleaning. 

>> To understand the relationship between the features of the dataset and the target variable `critical_temp`, we make use of scatterplots and correlation matrices. Samples of some scatterplots are shown below: 

<br>

<!-- ![plot1](img/plot1.jpeg "") ![plot2](img/plot2.jpeg "")

![plot3](img/plot3.jpeg "") ![plot4](img/plot4.jpeg "") -->

<p float="center">
<figure>
  <img style="text-align: center;" src="img/plot1.jpeg" height="300" width="330" class="center">
  <br>
  <img style="text-align: center;" src="img/plot2.jpeg" height="300" width="330" class="center">
  <br>
  <img style="text-align: center;" src="img/plot3.jpeg" height="300" width="330" class="center">
  <br>
  <img style="text-align: center;" src="img/plot4.jpeg" height="300" width="330" class="center">
</p>

<br>

>> As can be seen, we do not observe distinct linear patterns emerge between the features with `critical_temp`, but in the case of some features, observe an increasing or decreasing trend. The values in the correlation matrix support this fact, as those features show a reasonably high absolute value of correlation with `critical_temp`, indicating some amount of linear dependence. 

<br>

<!-- <p align="center"> -->
<img style="text-align: center;" src="img/corr_hist.jpeg" height="300" width="330" class="center">

<!-- ![corr_hist](img/corr_hist.jpeg "Correlation histogram for critical_temp")   -->
<br>

__3. Methods__

<br>

__3.1 Baseline - Linear Regression__

- <u>Brief description of the method</u>: We began by implementing the baseline model, which in this case is a multivariate linear regression model. The data was split into 80% training and 20% testing as is usually recommended, while maintaining reproducibility with a randomness seed value of 42. Upon running this, we got an $R^2$ score of 0.7225 (approx.). We then obtained a cross validation score on the training dataset with 5 folds, which was 0.7173577593955325 +/- 0.009265942222307403. The ~0.9% deviation shows that the model is not very sensitive to small changes in the data, and overall adapts quite well to new instances. 

<br>

__4. Experiments & Results__

<br>

__4.1 Protocol__

- <u>Details about splitting into training and testing datasets</u>: The data was split into 80% training and 20% testing, and reproducibility was added with a seed value of 42. 

- What kind of preprocessing was done to the dataset.  
* Data cleaning - The dataset was searched for missing values and duplicates, which were dropped if found.  
* Feature Scaling / Feature Reduction / Feature Selection - (TBD after consulting with Sir)

From the EDA, we notice that most of the columns (about 3/4th) have an absolute correlation above 0.261 with critical_temp upon observing the correlation matrix. We hence decided to apply feature reduction to the dataset in order to boost the speed of computation by removing less relevant features. We hence got the absolute values of the correlation values with `critical_temp`, and eliminated about 25% of the columns that were correlated by less than ~0.261. 

<br>

__4.2 Results__

- <u>Baseline results</u>: 

- <u>Include tables and figures (plots) for various experiments</u>: 

<br>

__5. Discussion__

- Not required in first draft

__6. Conclusion__

- Not 