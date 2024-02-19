# Public Opinion on Legalizing Abortion
Group1Project1
Group Members: Katherine Driebe (kad5fwz), Ramya Tangirala (rt4an), and Lasata Tuladhar (lt9vx)

The topic that this project will be focusing on is public opinion on the legalization of abortion. The text-type dataset used is Release 3 (R3) from the General Social Survey (GSS), published in May 2021 [1]. The raw data includes demographic information on the survey participants and their attitudes and opinions on different political issues, such as the environment, crime, and immigration. 

Our group subsetted the original data to only include the variables necessary for our analysis [2]. The link to our full data dictionary can be found here: 
[Data Dictionary](/DATA/Data_Dictionary.md)

Our initial stance was that among the variables shown in our data dictionary, religion would be the top factor in influencing the public opinion on abortion. However, after our exploratory analysis, we discovered that there were other factors that were causing relevant correlations. The updated hypothesis for our project is as follows: **While _religion_ is a significant factor influencing public opinion on legalizing abortion, _political affiliation_ and _age_ are also crucial determinants. The interplay between these variables may provide a more comprehensive understanding of the public's stance on abortion.** 

This project overall is targeted towards campaigners so they can better understand voter habits and be effective in their campaigns.

## Section 1: Software and Platform
For this project, our group attempted to download the R3 data directly from the GSS website [3]. However, the only file formats available were SAS, STATA, and SPSS. None of the three file formats were conducive to our Python script, which we were working on using Google Colab. To readjust, we downloaded the text data into a `.csv` format from a separate GitHub repository [4].

After receiving the data and downloading it into our Python script in Google Colab, we imported the following packages: `pandas`, `numpy`, `matplotlib.pyplot`, `seaborn`, `accuracy_score` from `sklearn.metrics`, `train_test_split` from `sklearn.model_selection`, `OneHotEncoder` from `sklearn.preprocessing`, and `DecisionTreeClassifier` and `plot_tree` from `sklearn.tree`. All of the code was run on two different Lenovo laptops, both supporting the Windows platform, and a Macbook Pro laptop supporting the MacOS platform.

## Section 2: Documentation Map
Our Project 1 repository is titled Group1Project1. It contains three folders (SCRIPTS, DATA, and OUTPUT), a MIT LICENSE file, and a README.md file. The SCRIPTS folder contains a master script which contains all the code needed to reproduce our data and analysis. The DATA folder contains the original dataset and the modified dataset used for the analysis. The OUTPUT folder contains all the exploratory plots, the classification tree model, and the evaluation metrics.

## Section 3: Reproduction of Results
Below is a step-by-step procedure of how to reproduce our group’s results:

1. Obtain the GSS R3 data from the following link: https://github.com/DS3001/project_gss [4]. The data must be downloaded in three chunks (parquets) due to the size of the dataset.

2. Subset the data so that only the variables relevant to the hypothesis are present: income, age, political views, political party, year, religion, region, personal opinion, pro-life or pro-choice, and sex. Also, limit the data to the year 2021 in order to ensure only data points from R3. This should reduce the size of the dataset from over 70,000 data points to around 4,000. 

3. Clean the data by removing NA values and outliers. 

4. There will be three opinions (distributions) of our data: pro-choice (PROCHOIC), pro-life (PROLIFE) and legalizing abortion for any reason (ABANY). Start with PROCHOIC by formatting the data into different `pandas` dataframes. 

5. One-hot encode (using the `sklearn.preprocessing` library) the categorical variables. The goal is to create a predictive model by decision tree, so split the data into training and testing sets.

6. Find and print the best maximum depth of the decision tree that will yield the highest accuracy of the classification model. Plot the training and testing sets on a simple stacked line plot. 

7. Create and display the decision tree for the PROCHOIC distribution. Create predictions on the test set and display the model’s accuracy. Improve the model accuracy by adding or dropping variables from Step 4.

8. Repeat steps 4-7 for the PROLIFE and ABANY distributions. These are the results for each model: PROCHOIC model accuracy = ~0.422, PROLIFE model accuracy = ~0.359, ABANY model accuracy = ~0.665.

9. For cross-validation, create plots in order to check if the correlation between the variables supports the classification tree model. Examples of these plots include: distribution of PROCHOIC and PROLIFE opinions, opinions grouped by religion, political views, age and sex, political affiliation, age distribution of the opinions, and the opinions over 2021.

## References (IEEE Format):
- [1] “GSS 2021 Codebook” gss.norc.org. https://gss.norc.org/Documents/codebook/GSS%202021%20Codebook.pdf

- [2] “R3 Release Variables” gss.norc.org. https://gss.norc.org/Documents/other/R3%20Release%20Variables.pdf 

- [3] “Get GSS Data | NORC” gss.norc.org.
https://gss.norc.org/get-the-data 

- [4] “Project GSS” github.com
https://github.com/DS3001/project_gss
