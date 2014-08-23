Exploring Titanic Dataset
========================================================
author: Siddharth
date: 23 Aug 2014
transition-speed:fast
transition: linear
DDP Course Project Submission

Background
========================================================



- The sinking of the Titanic is a famous event, and new books are still being published       about it.  
  
    
      
- Many well-known facts from the **proportions of first-class passengers to the ‘women and children first’ policy, and the fact that that policy was not entirely successful in saving the women and children in the third class are** reflected in the survival rates for various classes of passenger.

Mosaic Plot- survival by category
========================================================

```r
data(Titanic);require(graphics)
mosaicplot(Titanic, main = "Survival on the Titanic")
```

<img src="Exploring Titanic Dataset using interactive web app -DDP CP-figure/unnamed-chunk-1.png" title="plot of chunk unnamed-chunk-1" alt="plot of chunk unnamed-chunk-1" width="\maxwidth" />


Probability of survival in a category
========================================================
Following logic is used to give a percentage chance .Note that Class,Sex,Age are user inputs for the web app.  
Output is simply : survived*100 /(survived + died)

```r
data(Titanic)
  df<-as.data.frame(Titanic)
  save<-df[df$Class=="2nd"
           &df$Sex=="Male"
           &df$Age=="Adult"
           &df$Survived=="Yes","Freq"]
  tot<- save +df[df$Class=="2nd"
                 &df$Sex=="Male"
                 &df$Age=="Adult"
                 &df$Survived=="No","Freq"]
  100*save/tot
```

```
[1] 8.333
```

Summary
=============
- Roughly 35% of the passengers were female, so the first split of the mosaic plot is 35/6.  
  
- Among females, 67% survived and 33% died .Among males, only 17% survived.

- The survival rate is best among first class passengers and worst among third 
class passengers. 

**Further reading**
  [www.math.yorku.ca/SCS/friendly.html#mosaics](www.math.yorku.ca/SCS/friendly.html#mosaics)
