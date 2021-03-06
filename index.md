---
title: "Selecting your car engine type"
author: "d1m2r3"
highlighter: highlight.js
output: pdf_document
job: Active learner
knit: slidify::knit2slides
mode: selfcontained
hitheme: tomorrow
subtitle: Project for Developing Data Products - Coursera
framework: io2012
widgets: []
---

##  The impact of number of cylinders

1. When selecting a car, we get carried away by sales-speak about the number of cylinders
2. But, do we understand how the number of cylinders affect us?
3. The number of cylinders in the  car engine impacts fuel economy and power
4. More cylinders in the engine mean more power, but  fewer miles per gallon
5. Now, we will see this trade-off, based on real data!   

Here is the heart of the server calculation

```r
data(mtcars)
n1 <- 4 #Set it to the value input by the user
m1 <- mtcars[mtcars$cyl == n1,]; #Select all rows that have "n1" cylinders
mean(m1$mpg); mean(m1$hp)  #The subset data frame m1 is reactive
```

```
## [1] 26.66364
```

```
## [1] 82.63636
```

--- .class #id 

## A simple application  on "mtcars" dataset of R

1. RStudio contains a simple, small dataset "mtcars" on the performance of cars
2. A very useful, compact data set of about 11 parameters of car performance, for 32 types of cars
3. We will quantitavely study how  average fuel economy and power vary with number of cyliders
4. I have developed a simple application that tells you the mileage and power for a given number of cylinders
5. Developed with "shiny" package of RStudio
6. No programming for you, just go ahead and use!

---

## How to use this application

1. I hope you know how to start up RStudio, and copy files to your current directory
2. Copy the "ui.R" and "server.R" files to your current directory in RStudio
3. Ensure that the "shiny" package is installed under RStudio
4. Just issue the command "runApp()"; use "runApp(display.mode = "showcase")" if you want to see the code too!
5. You will see a browser window open from RStudio; the text should be self-explanatory
6. Just  enter the number of cylinders (4, 6, or 8) in the box provided, and out come the 
average miles per gallon and horse power
7. It is that simple!

---
## Application design (if you are interested)

1. This shiny app closely follows the instructions in the Coursera "Developing Data Products " lectures
2. The R script "ui.R", collects the basic input (number of cylinders), and feeds it 
the "server.R" script, and displays the results given by server.R
3. The R script "server.R" does the bulk of the work; it loads the "mtcars" data,
and subsets its once on the number of cylinders chosen by the user.
4. It calculates the average fuel economy (mpg) and power (hp), for all car types with the given number of cylinders
5. The script "server.R" uses a reactive response, so that the mtcars data frame is accessed only once for both mpg and power calculation



