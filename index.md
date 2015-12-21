---
title       : Data Product Development Project
subtitle    : Determining A Final Exam Grade
author      : Dr. C. Kelly
job         : Chemistry Instructor and Academic Advisor
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      #
widgets     : [mathjax, quiz, bootstrap, interactive]            # {mathjax, quiz, bootstrap}
bg          : #c1d192
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---
        
### <span style='font-weight:bold; color:darkblue; text-align:center;'>Tell me more about this app please!</span>

       
<span style='font-weight:bold;font-style:italic;'>Background: </span>
        
<p style='font-size:16px;'>As a college chemistry instructor for nearly 30 years, I routinely address the question "What do I need on the final to pass this class?" With this app a student can see exactly what they need on the final exam to get the course grade they want or need.  </p>
        
<span style='font-weight:bold;font-style:italic;'>Who would use the app? </span>
<p style='font-size:16px;'>Students and instructors.  </p>
        
<span style='font-weight:bold;font-style:italic;'>What do they need to run the app? </span>
<p style='font-size:16px;'>Just the points they've earned on three exams and homework assignments. </p>

<span style='font-weight:bold;font-style:italic;'>What do they get out? </span>
<p style='font-size:16px;'>The final exam score needed to achieve their desired course grade AND a predicted final exam score that allows them to realistically assess the possibility of achieving that grade. The app could be a wake-up call for students such that they put more effort into preparing for the final or adjust their expectations about the course outcome. </p>

---

### <span style='font-weight:bold; color:darkblue;text-align:center;'>How was the App developed?</span>

<p style='font-size:16px;'>Based on the self-reported exam and homework scores, and the student's desired final course outcome, a simple difference calculation reveals the points needed on the final exam. Assuming 1000 total points in the course, and only these 4 graded items, the points needed on the final exam is given by:</p> 

<p style= 'font-size:20px; color:darkblue; text-align:center;'>
Final Exam Points = (desired %)(1000 pts) - (Points from Exams & Homework)  </p>

<p style='font-size:16px;'>This value is easily expressed as a percentage by dividing by 250, the total possible points on the final exam.</p>
        
<p style='font-size:16px;'>Over many years of teaching general chemistry I had noticed that students typically scored lower on the final exam than the average of their 3 exams. Why? It's difficult for students to retain a semester's worth of knowledge for a cumulative exam and finals are stressfull. So performance if often less than what students think they can do. It's valuable for the students to see what final exam score is predicted based on the performance of previous students with similar scores going into the final. For the predictive portion of the app, final exam scores for the years 2006 - 2015 were fitted to 15 models using linear regression, CART and random forest fitting methods; the data file and R code for this analysis are in the github repo. The model with the greatest R squared value was the linear regression model using all three exams as predictors for the final exam score.</p>
        
<p style='font-size:16px;'>The coefficients for the line of best fit for the chosen model were extracted and used in the app to predict the student's final exam score based on their self-reported exam scores. </p>

---  &radio

### <span style='font-weight:bold; color:darkblue';> Predicting Your Final Exam Score</span>

Students tend to over-estimate their final exam scores. Data in my classes since 2009 indicate that about 72% of students score lower on the final exam than the average of their three semester exams. Suppose you had the following exam scores: 56%, 72% and 68%. What do you think is a reasonable prediction for your final exam score? Remember you plan to study REALLY hard for the final!!

1. 65.7%
2. 82.3%
3. _60.9_
4. 70.0%

*** .hint

The predicted average will be less than the numeric average of the three exam scores.
*** .explanation

Using the predictive model built for this class, and in the app as well, a value of 60.87% is calculated.

$$Predicted Final Exam Score = 0.28875*Exam I  + 0.20718*Exam II + 0.43496*Exam III = 60.87142$$

---

### <span style='font-weight:bold; color:darkblue';>Conclusions</span>
<p style='font-size:16px;'>The linear regression model used to fit the 3 individual exam scores to the known final exam score had an R squared value of 0.9844 (when going through the origin). This fit has a quite favorable predicitive ability and therefore is of great value when trying to get students to think about their final exam grade and hopefully inspiring (or scaring!) them into putting significant effort on that all-important exam.</p>

<p style='font-size:16px;'>Being very much a novice in the Data Science and R world, this project was sufficiently challenging for me....I know much more exciting projects and apps are being created by others in the community. But this project gave me something useful as we entered the end of the semester. It was an eye-opener to run the app for a student and show them what they may well be looking at for their final exam grade! I'll use anything I can to get them fired up to do well on the exam and have a successful course outcome.</p>
