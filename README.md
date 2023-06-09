# Implementation in R of the WISP Multiple Criteria Sorting Method

[![R-CMD-check](https://github.com/dioubernardo/rwisp/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/dioubernardo/rwisp/actions/workflows/R-CMD-check.yaml)
[![CRAN release](https://www.r-pkg.org/badges/version/rwisp)](https://cran.r-project.org/package=rwisp)

This project consists of the implementation of the method in R, its tests, the CRAN package and a web application written in R Shiny.

If you just want to run the method by reading the data contained in a CSV file, use the application hosted at shinyapps.io.
[Open rwisp on shinyapps.io](https://bernardosilva.shinyapps.io/rwisp/)

The web application repository is [github.com/dioubernardo/rwispweb](https://github.com/dioubernardo/rwispweb)

## Reference

Stanujkic, D., Popovic, G., Karabasevic, D., Meidute-Kavaliauskiene, I., & Ulutaş, A. (2023). An Integrated Simple Weighted Sum Product Method—WISP. IEEE Transactions on Engineering Management, 70(5), 1933–1944. doi: [10.1109/TEM.2021.3075783](https://doi.org/10.1109/TEM.2021.3075783)

Stanujkić, D., Karabašević, D., Popović, G., Zavadskas, E. K., Saračević, M., Stanimirović, P. S., Ulutaş, A., Katsikis, V. N., & Meidute-Kavaliauskiene, I. (2021). Comparative Analysis of the Simple WISP and Some Prominent MCDM Methods: A Python Approach. Axioms, 10(4), Article 4. doi: [10.3390/axioms10040347](https://doi.org/10.3390/axioms10040347)

Abstract: Until now, many different multiple criteria decision-making methods have been proposed for the facilitation of different business problems such as entrepreneurial. It can be noticed in the literature that some multiple criteria decision-making methods, mostly newly proposed, are based on certain forms of integration of weighted sum and weighted product approaches. This group of methods is also characterized by using different normalization procedures as well as different approaches used for dealing with non-beneficial criteria. Therefore, in this article, a new approach for selecting the most acceptable alternative is considered, which is based on the integration of weighted sum and weighted product approaches. The basic idea of the newly proposed approach is partly based on the MULTIMOORA method, but also includes some features of the WASPAS and CoCoSo methods. The proposed method is tested by using two illustrative examples borrowed from the literature that are related to the contractor and industrial robot selection. Additionally, to test its reliability, the obtained results are compared with the ones gained by using the MCDM methods of the first and second generations. Also, the stability of the proposed method is checked by varying the weights of the criteria. The proposed method predicts the application of a much simpler normalization procedure, involves four utility measures for defining the overall utility of alternatives, and enables a much easier ranking of them. The final conclusion is that the simple WISP method is easy to use and contributes to the increasing of the reliability of decisions that are made. Therefore, the proposal uses a much simpler normalization procedure, i.e. four utility measures for determining the overall utility of alternatives, and allows a much easier ranking of alternatives.

Note: When we study the articles of the method we will see that the rewriting equations of the utility values diverge in their equations, in exchange of emails with Dragisa Stanujkić, I was informed that it was an update of the method and that the most recent equations should be used.

## For Use

### Install option 1 - from github
```
library("devtools");
install_github("dioubernardo/rwisp");
library("rwisp")
...
```

### Install option 2 - from CRAN
```
install.packages("rwisp")
library("rwisp")
...
```

### Calculation option 1 - from vars
```
alternatives <- c("A1", "A2", "A3", "A4", "A5")
optimizations <- c("max", "min", "max", "max", "min", "max", "min", "max", "min", "max")
weights <- c(0.07, 0.07, 0.07, 0.14, 0.2, 0.08, 0.12, 0.125, 0.05, 0.075)
data <- matrix(c(
  c(3, 4, 6, 5, 2), # criterion 1 values
  c(7, 6, 4, 6, 8), # criterion 2 values
  c(4, 5, 5, 6, 3), # criterion 3 values
  c(4, 5, 6, 5, 4), # criterion 4 values
  c(6, 5, 4, 3, 6), # criterion 5 values
  c(4, 5, 5, 6, 3), # criterion 6 values
  c(6, 5, 5, 4, 6), # criterion 7 values
  c(8, 8, 9, 7, 7), # criterion 8 values
  c(5, 6, 7, 8, 7), # criterion 9 values
  c(8, 9, 9, 9, 8) # criterion 10 values
), nrow=5, ncol=10)

result <- wispcalc(data, alternatives, optimizations, weights)
print(result)
```

### Calculation option 2 - from CSV
```
result <- rwispfromcsv("example.csv")
print(result)
```


