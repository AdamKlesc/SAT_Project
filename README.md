# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Test Analysis by Adam Klesc


## Overview

This project covers:
- Basic statistics and probability
- Many Python programming concepts
- Programmatically interacting with files and directories
- Visualizations
- EDA
- Working with Jupyter notebooks for development and reporting

The SAT is a standardized test that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)).
* [SAT](https://collegereadiness.collegeboard.org/sat)

The SAT changed their format in 2016 to address some problems that students and schools had with their style of questions and questionable grading. The ACT surpassed the SAT in popularity due to these problems and a perception that the SAT was "class-biased" due to their questions. The ACT also did this through a lot of states make it free state-wide and a requirement to pass high school which the SAT did not catch up on.

---

## Problem Statement

When crafting my problem statement, I really was stuck with what to really analyze and what problem to solve. But it really simplified the process for me when looking at the yearly datasets because looking at the years and the progression of both the SAT and ACT participation rates, it really clicked.

My problem statement in a short sentence is: 

### Has collegeboard solved the problems they were seeking to fix with the 2016 format change?

I really had to go through three factors when making my problem statement. Who is my audience, what data am I using, and what value am I bringing to my audience. 

* The first factor was fairly easy to answer, I think the people who would be most interested in the answer to my problem statement would be collegeboard and the people involved in the change to see whether their change has actually worked. 

* The second factor was what data I would use and primarily I would be using the SAT 2017-2019 data along with the ACT 2017-2019 data but over the course of the project, I added some outside sources as well.

* The final factor in creating that problem statement was bringing clarity to the changes and whether they have been actually productive in solving what they were mean't to solve.

---

## Datasets

### Provided Data

These are the datasets I used in the process that were included in the data folder provided, I cleaned each of them but will still be sharing both the raw and cleaned datasets

* [`act_2017.csv`](./data/act_2017.csv): 2017 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`act17newclean.csv`](./data/cleaned_data/act17newclean.csv): Cleaned version of [`act_2017.csv`](./data/act_2017.csv)
* [`act_2018.csv`](./data/act_2018.csv): 2018 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`act18newclean.csv`](./data/cleaned_data/act18newclean.csv): Cleaned version of [`act_2018.csv`](./data/act_2018.csv)
* [`act_2019.csv`](./data/act_2019.csv): 2019 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`act19newclean.csv`](./data/cleaned_data/act19newclean.csv): Cleaned version of [`act_2019.csv`](./data/act_2019.csv)
* [`sat_2017.csv`](./data/sat_2017.csv): 2017 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat17newclean.csv`](./data/cleaned_data/sat17newclean.csv): Cleaned version of [`sat_2017.csv`](./data/sat_2017.csv)
* [`sat_2018.csv`](./data/sat_2018.csv): 2018 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat18newclean.csv`](./data/cleaned_data/sat18newclean.csv): Cleaned version of [`sat_2018.csv`](./data/sat_2018.csv)
* [`sat_2019.csv`](./data/sat_2019.csv): 2019 SAT Scores by State ([source](https://blog.prepscholar.com/average-sat-scores-by-state-most-recent))
* [`sat19newclean.csv`](./data/sat19newclean.csv): Cleaned version of [`sat_2019.csv`](./data/sat_2019.csv)


### Additional Data

These are the datasets I required from outside research I performed.

* [`PopulationcsvData.csv`](./data/PopulationcsvData.csv): Population rankings by State ([source](https://worldpopulationreview.com/states))
* [`populationrank.csv`](./data/cleaned_data/population2019rank.csv): Cleaned version of [`PopulationcsvData.csv`](./data/PopulationcsvData.csv)
* [`gdp2019rank.csv`](./data/cleaned_data/gdp2019rank.csv): Dataframe created on Python using outside sources on GDP Rank by state in 2019 ([source](https://www.statista.com/statistics/248063/per-capita-us-real-gross-domestic-product-gdp-by-state/))
* [`actfreecols.csv`](./data/cleaned_data/actfreecols.csv): Dataframe created on Python using outside sources on states that have the ACT free statewide ([source](https://blog.collegevine.com/states-that-require-the-act/#list))
* [`satfreecols.csv`](./data/cleaned_data/satfreecols.csv): Dataframe created on Python using outside sources on states that have the SAT free statewide ([source](https://blog.collegevine.com/states-that-require-sat/))
* [`acttotalclean.csv`](./data/cleaned_data/actfreecols.csv): Dataframe from the merged dataframes related to the ACT + the additional data
* [`sattotalclean.csv`](./data/cleaned_data/satfreecols.csv): Dataframe from the merged dataframes related to the SAT + the additional data

---

### Data Dictionary

A dictionary compiling the primary columns from the two main datasets used throughout the analysis.

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**participation17**|*float*|SATTotal|Participation numbers for the 2017 SAT(in decimal percentage)|
|**participation17**|*float*|ACTTotal|Participation numbers for the 2017 ACT(in decimal percentage)|
|**participation18**|*float*|ACTTotal|Participation numbers for the 2018 ACT(in decimal percentage)|
|**participation18**|*float*|SATTotal|Participation numbers for the 2018 SAT(in decimal percentage)|
|**participation19**|*float*|SATTotal|Participation numbers for the 2019 SAT(in decimal percentage)|
|**participation19**|*float(|ACTTotal|Participation numbers for the 2019 ACT(in decimal percentage)|
|**total17**|*int*|SATTotal|Average total score for the 2017 SAT(median score)|
|**total18**|*int*|SATTotal|Average total score for the 2018 SAT(median score)|
|**total19**|*int*|SATTotal|Average total score for the 2019 SAT(median score)|
|**composite17**|*float*|ACTTotal|Average total score for the 2017 ACT(mean score)|
|**composite18**|*float*|ACTTotal|Average total score for the 2018 ACT(mean score)|
|**composite19**|*float*|ACTTotal|Average total score for the 2019 ACT(mean score)|
|**sat_free**|*boolean*|ACTTotal/SATTotal|States that have the SAT free statewide|
|**act_free**|*boolean*|ACTTotal/SATTotal|States that have the ACT free statewide|
|**population_rank**|*float*|ACTTotal/SATTotal|Population rank for each state|
|**gdp_rank_19**|*float/int*|ACTTotal/SATTotal|GDP rank for each state|
|**state**|*object*|SATTotal|The states where the data is located|
|**state**|*object*|ACTTotal|The states where the data is located|

---

## Deliverables

### Notebook that contains my cleaning of data and creation of new CSV's
[`cleaning_and_creating.ipynb`](/cleaning_and_creating.ipynb)
### Notebook that contains my analysis and visualization
[`visualization_and_analysis.ipynb`](/visualization_and_analysis.ipynb)
### Starter Code
[`starter-code.ipynb`](/code/starter-code.ipynb)
### ReadMe
[`README-ADAMK.md`](/README-ADAMK.md)
### Presentation
[`project_1_presentation.pdf`](/project_1_presentation.pdf)

---

### Technical Report Starter Code


Edited structure of starter code notebook by creating individual notesbooks for cleaning and analysis + visualization.
Starter code trials are complete either in those two notebooks or on the starter code itself

### Notebook that contains my cleaning of data and creation of new CSV's
[`cleaning_and_creating.ipynb`](/cleaning_and_creating.ipynb)
### Notebook that contains my analysis and visualization
[`visualization_and_analysis.ipynb`](/visualization_and_analysis.ipynb)
### Starter Code
[`starter-code.ipynb`](/code/starter-code.ipynb)


---

### Analysis

The analysis started with understanding the problem statement, in order to do that, I had to find out the reasons why the SAT changed and look at those problems in isolation each when looking at the data to see if collegeboard has actually succeeded in solving the problems they tried to address with their change.

* Increase participation to overtake the ACT in market-share

* Eliminate the stigma that the SAT is class-biased and is unfair towards those of lower incomes

I narrowed it down to these two problems because of these two sources 

[greentestprep](https://greentestprep.com/resources/sat-prep/new-sat-march2016/why-is-the-college-board-changing-the-sat/)


[cnn.com](https://www.cnn.com/2014/03/05/living/sat-test-changes-schools/index.html)

These sources really helped clarify what the SAT was actually looking to achieve with their change and helped me in my data collection process

* From looking at the mean and median, it was evident that the SAT was steadily gaining popularity while the ACT was losing popularity but what makes the change a great success in terms of the first problem the change was mean't to address was how the SAT was significantly more popular than the ACT in states with a higher population. The SAT has also notably been made free in 3 states after 2017 (the first full year of the SAT change), those states being Colorado, West Virginia, and Illinois. New Hampshire, Michigan, and Connecticut also made a switch to the SAT, the year of the change. It's clear that the SAT change has done wonders in improving participation and making states believers in their test.

* This lines up with [outside sources](https://theolivebook.com/sat-vs-act-which-is-more-popular/#:~:text=As%20of%202019%2C%20the%20SAT,students%20who%20took%20the%20ACT) claiming that the SAT surpassed the ACT in 2019 with overall market share with 2.2 million students to the ACT's 1.8.

* From looking at the correlation between the GDP per state + SAT Participation, it was clear to see that the change had not had the effect that was desired from collegeboard execs. The coefficient stayed the same despite the added help in a new Khan Academy course that was free to all + fee waivers (for college applications) for those who met a certain income threshold. [source](https://www.cnn.com/2014/03/05/living/sat-test-changes-schools/index.html)

* [While a lot of studies tend to disagree on the fact that the SAT is a class-biased test](https://www.ivyscholars.com/2021/06/11/are-the-sats-biased/), it is clear that a lot of universities are taking note of the potentially inherent class disadvantage in standardized testing as a whole and have outright banned it not only for just times of a pandemic, but also for the foreseeable future. The most prominent of these universities being the [University of California](https://edsource.org/2021/university-of-california-must-drop-sat-act-scores-for-admissions-and-scholarships/654842)

---

### In Conclusion

From my analysis, I was able to conclude that the SAT has successfully managed to overtake the ACT once again as the market leader in standardized testing due to primarily to the SAT changes made to the format and structure. It not only made the test more appealing to students but also states themselves as number of them made it free during the time between 2019 from the date of the change. This is evidenced by the fact that the SAT once again, became the market-leader in standardized testing after the ACT's regression post-SAT change. While solving participation was a massive success in both participation numbers and time, the second problem is where the SAT still needs work.

The SAT change partially occurred due to the reputation that the SAT was a class-biased test, the strange scoring of the 2400 scale and detachment from the actual school work that students were learning in school lead to the ACT being more popular and while they did fix the problem with participation, the lingering problem of class-bias is still there. With more colleges pulling away from standardized testing and geographical location being so heavily tied to participation and success, there need to be more upcoming changes to rectify this issue and make the SAT a more equitable test.
