Elementary Statistics With R
========================================================
author: Rebekah Robinson and Homer White, Georgetown College
transition:  none
transition-speed:  fast
navigation: slide










Our Intended Audience
=================

Instructors with

* some user experience with R
* who have studied the [Project Mosaic](http://mosaic-web.org) approach to teaching elementary statistics with R

Useful eCOTS 2014 sessions:

* [*Effective Teaching using R, RStudio, and the MOSAIC Package*](https://www.causeweb.org/ecots/workshop/6.php)
* [Planting Seeds of Reproducibility in the Introductory Statistics Course with R Markdown](https://www.causeweb.org/ecots/breakout/cetinkaya-rundel.php)
 
 

```r
install.packages("mosaic")
```



mosaic/tigerstats approach
=====================

Gentle down the coding!


* minimize number of functions to know
* provide uniform user interface for those functions
* don't force students to write their own functions
* pay little attention to types of R objects
* avoid teaching flow-control structures



The Tigerstats Package
=======================


```r
install.packages("devtools")
library(devtools)
install_github(repo="tigerstats",
          username="homerhanumat")
```


* Used alongside of package `mosaic`
* Customize output to GC course objectives
* Alternative function help (Course Notes, blog posts)
* Simulation with manipulate/Shiny apps
* `tigerstats` source code is [here](https://github.com/homerhanumat/tigerstats).





Some Tigerstats Features
============================

Uniform function template for both descriptive and inferential procedures:

$$procedure(Formula,data=Mydata,\ldots)$$

Formulas are of four types, based on nature of variables in one's "Research Question."

Output is customized to GC course objectives.  Paradigmatic examples:

* [`chisqtestGC()`](http://statistics.rainandrhino.org/blog/2014/02/01/chisqtestGCtutorial/)
* [`ttestGC()`](http://statistics.rainandrhino.org/blog/2014/02/27/ttestGCtutorial/)
* [`lmGC()`](http://statistics.rainandrhino.org/blog/2014/02/15/lmGCtutorial/)



Course Materials
============

* [Course Notes](http://statistics.georgetowncollege.edu/notes/ch1.html) integrated with R-code-instruction
* `knitr` package converts R Markdown to HTML, pdfLaTeX
  * R Markdown [Homework assignments](http://statistics.rainandrhino.org/blog/2014/05/02/perl-scripts-r-studio/)
  * [Lecture slides](http://statistics.georgetowncollege.edu/slides.html) start as R Presentation documents
  * Student data analysis reports start in R Markdown, [convert to other formats](http://statistics.rainandrhino.org/blog/2014/02/01/pander-for-pretty-conversion-on-the-r-studio-server/)
* Further tools for automated production of materials:
  * [Pandoc](http://johnmacfarlane.net/pandoc/) for Course Notes, [Octopress](http://octopress.org/) for [blogging with R](http://statistics.rainandrhino.org/blog/2014/04/13/roctopress/)
  * New and promising:  [GitBook](http://www.gitbook.io/) with Jason Bryer's [`Rgitbook`](http://jason.bryer.org/Rgitbook/) package


Apps
==============

RStudio's `manipulate` package enables interactivity in the Plots pane.  (More info [here](http://statistics.rainandrhino.org/blog/2014/04/08/reasons-to-teach-with-R-2/).)

* Can be programmed to work with arbitrary datasets;


```r
CIMean(~height,data=imagpop)
```


The `shiny` package produces web applications.  (More info [here](http://statistics.rainandrhino.org/blog/2014/05/04/reasons-to-teach-with-R-3/).)

* More flexible user interface;
* Permits detailed explanation of learning activity;
* A bit more cumbersome for user to load datasets.

======================

<iframe src="http://rstudio.georgetowncollege.edu:3838/ShallowReg/" style="border: black; width: 1500px; height: 700px"></iframe>

Shiny Access Options
============

* Web-based (no R required), RStudio hosts:  [http://homer.shinyapps.io/ShallowReg](http://homer.shinyapps.io/ShallowReg)
* Web-based, set up your own Shiny server:  [http://rstudio.georgetowncollege.edu:3838/ShallowReg](http://rsudio.georgetowncollege.edu:3838/ShallowReg)
* (with `shiny`) fetch from Github repository, run locally:


```r
require(shiny)
runGitHub(repo="tigerstats",
    username="homerhanumat",
    subdir="inst/FindRegLine")
```


* (with `shiny`) run locally from installed package:


```r
runApp(system.file("SlowGoodness",
        package="tigerstats"))
```



Concluding Remarks
===================

Further Resources:

* Course website:  [http://statistics.georgetowncollege.edu](http://statistics.georgetowncollege.edu)
    * most course materials available here
* Blog:  [http://statistics.rainandrhino.org/](http://statistics.rainandrhino.org/)
    * includes Tech Notes for instructors

Remember:

* You don't need to use our package:  modify, and make your own!
* `tigerstats` = training wheels; students who move on in statistics should learn standard R functions












