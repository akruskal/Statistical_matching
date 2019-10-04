HDAT9700: Assessment 1A - Chapters 1 & 2
================

### Submission instructions

This is an R Markdown document—an example of *literate programming*, an
approach which allows users to interweave text, statistical output and
the code that produces that output.

To complete your assignment:

  - Edit this file directly, interweaving text and R code as appropriate
    to answer the questions below. Remember to `Knit` the file to make
    sure everything is running smoothly. Detailed information on R
    Markdown is available
    [here](https://rmarkdown.rstudio.com/lesson-1.html), and there is a
    useful cheatsheet
    [here](https://www.rstudio.com/wp-content/uploads/2015/02/rmarkdown-cheatsheet.pdf).

  - Use git to `commit` changes you make in this repo locally.

  - `Push` the repo, together with this edited file and the
    corresponding `.md` file to GitHub Classroom.

You can `commit` and `push` as often as neccessary—your assessment will
be graded on the most recent version of your repo at the assessment due
date.

Good luck\!

-----

### Overview

In this assignment you are provided with data on maternal
characteristics and birth outcomes. Your aim is to assess the causal
effect of maternal smoking during pregnancy on child’s birthweight.

The data come from [Abrevaya
(2006)](https://onlinelibrary.wiley.com/doi/abs/10.1002/jae.851)
*Estimating the effect of smoking on birth outcomes using a matched
panel data approach*. For the purposes of this assignment, the dataset
has been restricted to mother’s first birth. More details can be found
[here](http://qed.econ.queensu.ca/jae/2006-v21.4/abrevaya/readme.ja.txt).

#### Here is a brief description of the available variables:

  - **momid** identification number of the mother  
  - **idx** index number of a mother’s birth  
  - **mage** age of mother (in years)  
  - **gestat** length of gestation (in weeks)  
  - **birwt** birthweight (in grams)
  - **smoke** indicator variable for smoking status (1=smoker,
    0=nonsmoker)
  - **male** sex of the baby (1=male, 0=female)
  - **collgrad** college-graduate indicator (1=graduate, 0=non-graduate)
  - **black** indicator variable for black race (1=black, 0=white)

These data are contained in your assignment repo and can be read as
follows:

``` r
dat <- read.csv("smoking_data_first_born.csv", header=TRUE)
head(dat)
```

    ##   momid idx mage gestat birwt smoke male collgrad black
    ## 1    14   1   16     24  2790     0    0        0     1
    ## 2    25   1   23     41  2778     0    1        0     1
    ## 3    39   1   36     41  2948     0    1        0     0
    ## 4    48   1   30     39  2880     1    1        0     0
    ## 5    60   1   23     43  3714     0    0        0     1
    ## 6    71   1   20     40  3203     1    1        0     0

-----

### Assessment questions

1)  There are nine variables in the dataset. Select which variables you
    will consider for matching and justify your decision (10%)

2)  Using your chosen variables, match smokers to non-smokers using the
    matching specifications in (2a) and (2b). Briefly summarise the
    balance in both cases, drawing on appropriate numerical and
    graphical summaries.
    
    (2a) 3:1 nearest-neighbour matching using the propensity score
    distance metric (20%)  
    (2b) Coarsened Exact Matching (20%)

3)  Fit the model birwt ~ smoke in
    
    (3a) The raw data (5%)  
    (3b) the matched data, using your preferred match from 2a/2b (5%)

4)  Briefly describe the model results. How does the estimated effect
    for smoking change and why? (10%)

5)  Briefly argue whether or not the assumption of exchangeability is
    likely to hold in the implicit causal model underpinning 3b. (10%)

6)  These data come from an observational study. Imagine the **exact
    same data** arose from a Randomised Control Trial where mothers were
    randomised to smoke or not smoke during pregnancy (ignore the
    obvious ethical issues of such a trial for the sake of this
    question).
    
    (6a) What can you observe about the randomisation process? (5%)  
    (6b) How would the roll of background variables like mother’s race
    and education change in the analysis, given that the data came from
    an RCT? (15%)

-----

### Student declaration

***Instructions: Indicate that you understand and agree with the
following three statements by typing an x in the square brackets below,
e.g. \[x\].***

I declare that this assessment item is my own work, except where
acknowledged, and has not been submitted for academic credit elsewhere
or previously, or produced independently of this course (e.g. for a
third party such as your place of employment) and acknowledge that the
assessor of this item may, for the purpose of assessing this item: (i)
Reproduce this assessment item and provide a copy to another member of
the University; and/or (ii) Communicate a copy of this assessment item
to a plagiarism checking service (which may then retain a copy of the
assessment item on its database for the purpose of future plagiarism
checking).

  - \[ \] I understand and agree

I certify that I have read and understood the University Rules in
respect of Student Academic Misconduct.

  - \[ \] I understand and agree

I have a backup copy of the assessment.

  - \[ \] I understand and agree