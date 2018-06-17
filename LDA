
#Data
data("iris")
str(iris)

#Plot instances to see if they are linearly sepretable
library(psych)
pairs.panels(iris[1:4],
					gap=0,
					bg=c("red","green","blue")[iris$Species],
					pch=21)
					
					
# Data Partitioning
set.seed(555)
ind = sample(2, nrow(iris),replace=TRUE, prob=c(0.6,0.4))
training= iris[ind==1,]
testing= iris[ind==2,]

# Linear Discriminant Analysis
library(MASS)
linear= lda(Species~., data= training)

attributes(linear) # this shows values avilable about model

# Histogram
p= predict(linear, training)
ldahist(data= p$x[,1], g= training$Species)

# Bi-Plot
library(devtools)
install_github("fawda123/ggord")
library(ggord)
ggord(linear, training$Species)


# Partition Plot
 library(KlaR)
 partimat(Species~., data= training, method="lda")
 partimat(Species~., data= training, method="qda")
 
 # Confusion Matrix and Accuracy
 p1= predict(linear, training)$ class
 tab= table(Predicted= p1, Actual= training$Species)
 tab  # get us confusion matrix 
 
 









					
