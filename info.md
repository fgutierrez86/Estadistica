## Measure of central tendency
------------------------------

### Mode Moda

value that ocurrs most frecuently
most common outcome
nominal or ordinal measure

```R
    > moda(x)  // funcion realizada
```

### Median Mediana

The middle value of your observation
when arranged from smallest to largest
50% below the median, 50 above the median

```R
    > median(x)
```


### Mean Promedio

The sum of all the values divided by the 
number of observations

```R
    > mean(x)
```

## Distribution or dispertion
------------------------------

### Range

highest value - lowest value

```R
    > max(x) - min(x)
```

### Quartile

```R
    > quantile(x)
    > Q1 <- quantile(x)[2]
    > Q3 <- quantile(x)[4]
```

* 25%  Q1
* 50%  Q2
* 75%  Q3
* 100% Q4

### Interquartile range

Diferencia entre Q3 y Q1

```R
    > Q3 - Q1
```
## IQR

```R
 > IQR <- Q3 - Q1

> IQR(vector)
```


### Outliers: 

```R
    > #Lower:  
    > Q1 - 1.5*IQR(x)
    > #higher: 
    > Q3 + 1.5*IQR
```

### Box Plot

```R
    > boxplot(vector)
```

### Dot Plot
```R
> dotplot(vector)
```

### Variance

The variance tells you how far the scores
are spread out from the mean.

### standard deviation


![Image of sd](images/StandardDeviation.PNG)

```R
> sd(vector)
```

### Z-Score
![Image of ZScore](images/ZScore.PNG)
```R
> scale(x, center=TRUE, scale=TRUE)
```

## R
----

### ver estructura del objeto
```R
> str(x)
```
### ver dimensiones
```R
> dim(x)
```

### hacer una tabla de frecuencias (con un vector de factores)
```R
> table(mtcars$am)
```
### También se hace una tabla de contingencia cuando son dos variables:

Crea una tabla con row = tobacco column = student : 
```R
 > table(smoking$tobacco, smoking$student)
```

### hacer un grafico de barras con la tabla de frecuencias
```R
> barplot(table, ylab = "label y", xlab = "label x")
```
### hacer un histograma
```R
> hist(vector, main="titulo")
```

## Correlation and Regression
-----------------------------
### Correlation between two variables.



#### Contengency table
Used for nominal and ordinal variables. 

#### Scatterplot
Used for quantitative variables.
### Pearson's R
Measure of correlation.
Expresses the direction and strength of the linear
correlation between two variables with a single number.

Pearson's R is allways a number between -1 and 1.

Only for linear relation.

Formula:  

![Image of Pearsons](images/Pearsons.PNG)

Where:

* **Zx** Z Score of x variable.
* **Zy** Z Score of y variable.
* **x** Numbers of elements.

```R
    > cor(var1, var2, method="pearson")
# Pearson is the default method...
```



### Regression Line

![Image of Pearsons](images/LinealRegression.PNG)

### Compute regression line

![Image of Pearsons](images/ComputeRL.PNG)

### **r2** (squared 2) or correlation coefficient (wikipedia).

Tells yoy how much better a regression line predicts the value
of a dependent variable than the mean of the variable.

![Image of Prediction errors](images/PredictionError.PNG)

```R
        > money
         [1]  1  2  3  4  5  6  7  8  9 10
        > prosocial
         [1]  3  2  1  4  5 10  8  7  6  9
        > plot(money, prosocial)
        > abline(lm(prosocial ~ money))
        > lm(prosocial~money)

        Call:
        lm(formula = prosocial ~ money)

        Coefficients:
        (Intercept)        money  
             1.2000       0.7818  
```

![Image of Prediction errors](images/ComputingRegressionLine.PNG)


### Explained variance

**model assumptions**:
The centre of the Y distribution must be a linear function of X,
and for any given x, the Y distribution must be normal.
In this case, R2 is interpreted as proportion of explained variance.


![Image of Prediction errors](images/ExplainedVariance.PNG)

The left circle represents the variance of independent variable
X and the right circle stands for the variance of dependent
variable Y.The overlap represents **r-squared or the explained variance**




