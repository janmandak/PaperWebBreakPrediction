# Paper web break predicition

The objective of this task is to predict paper break before it occurs. We can consider this problem as an early classification problem. The dataset is provided by Ranjan et al (2018), who made accessible data collected from the network of sensors in a mill along with the unwanted events of paper breaks. Here is a brief information about the data set:

- it has 18,398 records,
- the frequency of the data is two minutes,
- time is the timestamp of the row,
- y is the binary dependent variable,
- x1-x61 are the predictors; all of them are continuous except of x61 (binary variable) and x28 (categorical variable),
- all predictors are centered.

Probably the most challenging is the fact that this classification task is highly unbalanced – the paper break occurred only 124 times out of 18,398 records. Ranjan et al (2018) proposed a straightforward approach for an early classification – simply move binary response variable up by k rows. They recommend that k should not be higher than 2. In this paper we moved y up by 2 rows and therefore we predict the event two period (4 minutes) ahead.

Feature engineering is typically important in this type of classification problem. Schfer and Leser (2017) have proposed a first difference of the predictors, representing a gradual change in a variable. However, the first derivative may not necessarily trigger the event. A second difference of a variable representing sudden change should be also tried. Besides the first and second differences Ranjan et al (2018) also suggested to create change of the level of the categorical variable x28, instead of the actual value. A binary variable x28change was created and is equal to 1 when the level of variable x28 in time t is different from the level in time t-1 and otherwise 0.

## References: 
Ranjan, Ch., Mustonen, M., Paynabar, K. and Pourak, K. (2018). ‘Dataset: Rare Event Classification in Multivariate Time Series’. arXiv preprint arXiv:1809.1071v2
