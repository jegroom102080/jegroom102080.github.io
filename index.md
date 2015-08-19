---
title       : Body Mass Index (BMI) Calculator
subtitle    :  (Use arrow keys to navigate)
author      : Jason E.Groom
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Intro & Motivation
Body Mass Index (BMI) is a simple index of weight-for-height that is commonly used to classify underweight, overweight and obesity in adults. It is defined as the weight in pounds divided by the square of the height in inches multiplied by 703 (lbs/in^2)*703.

Key facts:

Worldwide obesity has nearly doubled since 1980.
35% of adults aged 20 and over were overweight in 2008, and 11% were obese.
Obesity is preventable. WHO Obesity and Overweight Factwheet
Good Nutrition and regular phisical activity are vital for good health and disease prevention. 

## BMI diagnostics are measured as follows:
BMI <18.5 : Under Weight

BMI [18.5-24.9] : Normal Weight

BMI [25-29.9] : Over Weight

BMI >=30 : Obese

---
## How is BMI calculated?

There is a formula for calculating the BMI measure. The formula is the following:

BMI = weight(lbs) * 703/ height(inches)^2
Thus for the next example, the BMI will be:

```r
weight <- 220
height <- 71

(weight*703)/(height^2)
```

```
## [1] 30.68042
```

---

## Diagnostic
The function use for calculating the diagnostic is the following:


```r
diagnostic_f<-function(weight,height){
  BMI_value<-weight*703/(height^2)
  ifelse(BMI_value<12, "Check inputs, if correct you are severely under weight", 
         ifelse(BMI_value<18.5,"Under Weight",ifelse(BMI_value<25,"Normal",
                                                     ifelse(BMI_value<30,"Over Weight",
                                                            ifelse(BMI_value<60, "Obese", 
                                                                   "Check inputs, if correct 
                                                                   you are severely over
                                                                   weight")))))
}
```

This means that for the previous example of 220 pounds, and 71 inches, the diagnostic will be:


```r
diagnostic_f(220, 71)
```

```
## [1] "Obese"
```

---

## Conclusion

The BMI is a relatively easy, non-invasive way to establish weight status, and for most people, it relates reasonably well to a person's body fat.  

However, BMI is only a estemate for body fatness. Other things such as fitness can alter the relation between BMI and body fatness and must be taken into consideration. Lets consider a man that is very low body fat percentage. Because muscle is heavy, he may have a high BMI.  This is why it is only an estemate of a persons fatness. Also if a person has not been through puberty the measurment is not going to be accurate.  

