# Stat 88 Website

Website is at "stat88.org" and "stat88.github.io"

Based on Hyde (a Jekyll Theme)
![Hyde screenshot](https://f.cloud.github.com/assets/98681/1831228/42af6c6a-7384-11e3-98fb-e0b923ee0468.png)

## Overall

In the main directory of the repo, there are many `.md` files and `.html`. These files directly correspond to pages of the website. For example, `instructors.html` is what leads to the content of `stat88.org/instructors`. Similarly `about.md` corresponds to `stat88.org/about`. 

## instructors.html

This is where you will put the staff names, photos, sections, and office hours times. Staff photos need to be placed in the `/assets/images` folder.

## /\_data/announcements.yml

This is where you can put announcements that will be displayed on the top of the website. Only one announcement will be displayed at a time, so I usually just put one announcement.

## /\_includes/agenda.html

This is where you can alter which week displays on the top of the main page. Scroll to the bottom of the file. Change the `initialSlide` value.

## /\_data/syllabus2.yml

This yml file controls the course calendar on the main page. It is very easy to put assignments on here! Here is an example DataHub url: `http://prob140.datahub.berkeley.edu/hub/user-redirect/git-pull?repo=https://github.com/stat88/content-fa19&branch=master&subPath=hw/Homework_1.ipynb`. This works because `stat88/content-fa19` is a public repo and the path `hw/Homework_1.ipynb` exists in that repo. It's as simple as that!

## weekly.html

Controls the Google Calendars for office hours and for sections. We have two different calendars so that the events can be different colors.

# Old 140 Instructions

## Contents

- Changing Data
- Building and Pushing
- Development


## Content Developers

The system is designed to make it as easy as possible to update the syllabus/ other content

### Updating Course Information

All information is stored inside the **_data** folder (everything else is a template, and not worth tampering with)


If you're trying to clone this website for another class (or if attempting to make modifications to course details - instructors, TAs, and tutor names), then modify **_data/courseInfo.yml**

If you're attempting to change the syllabus, everything is contained in the **_data/syllabus/** folder. The operations that you can do are

1) Adding a new week's worth of content by creating a new **yml** file in the **_data/syllabus/** folder (simply copy an existing *week.yml* file, and modify as required)

2) Adding lectures within a week, or updating links inside the course; simply change the required thing in the file 


## Building and Pushing 

1) Make sure you have Ruby installed (and gem as a result)
2) Install the required plugins
    
    gem install jekyll jekyll-paginate

3) run your own server
    
    jekyll serve

or 

4) Export to HTML

    jekyll build


## Development

The Stat 88 website is sourced from Hyde, and is built on top of Jekyll. We attempt to minimize the number of modules used, and most of the customization to the site comes from the data files. Have fun playing around


## License

Open sourced under the [MIT license](LICENSE.md).

<3

## From Ashley: Script for creating fresh `syllabus2.yml`

This will have to be tweaked for the Spring, but I hope it'll be useful :) This will print out a `syllabus2.yml` (with all the proper dates and lecture titles). 

```
import datetime

lectureCount = 0
hwCount = 0

def getCompleteString(string):
  global lectureCount
  if not ("No school" in string or "Holiday" in string or "Midterm" in string):
    lectureCount += 1
    return "Lecture " + str(lectureCount) + ": " + string
  return string

def getPossibleQuiz(date):
  if date == '09/12':
    return "Quiz 1"
  elif date == '09/26':
    return "Quiz 2"
  elif date == "10/31":
    return "Quiz 3"
  elif date == "11/21":
    return "Quiz 4"
  elif date == "11/28":
    return "Holiday"
  elif date == "08/27":
    return "No school"
  return "Discussion"

def getPossibleHomework(date):
  global hwCount
  if date.strftime("%x")[:-3] == '10/07':
    return "No homework: Midterm"
  elif date.strftime("%x")[:-3] == '08/26':
    hwCount += 1
    return "HW " + str(hwCount) + " (Due Tues " + (date + datetime.timedelta(days=8)).strftime("%x")[:-3] + ' at 9 AM)'
  else:
    hwCount += 1
    return "HW " + str(hwCount) + " (Due Mon " + (date + datetime.timedelta(days=7)).strftime("%x")[:-3] + ' at noon)'


weekNames = ["Getting Started", "Conditioning", "Random Variables", "Random Variables and Expectation",
"The Power of Additivity", "Path to Prediction", "Midterm Week", "Variability", "Large Random Samples",
"Fundamentals of Inference", "Continuous Distributions", "Bias and Variance", "Introduction to Regression",
"The Error in a Regression Estimate", "Inference in Regression"]


lectureTitles = ["No school", "Course introduction; fundamentals", "Exact calculations, and bounds", "Holiday", 
"Intersections of several events", "Updating chances: Bayes' rule", "A closer look at independence",
"Random variables and their distributions: the binomial", "Simple random sampling",
"Exponential approximations", "The Poisson distribution", "Expectation", "Collections of random variables: joint distribution",
"Additivity of expectation; unbiased estimates ", "The power of Booleans: the method of indicators",
"Updating revisited: conditional distribution", "Expectation by conditioning", "Least squares prediction",
"Putting it all together: examples", "Midterm review", "Midterm", "Measuring variability", "Typical or unusual? Tails of distributions",
"The accuracy of a simple random sample", "Variability of a random sample sum", "The square root law and the law of averages",
"Central Limit Theorem", "Inference: confidence intervals based on the CLT", "Inference: testing hypotheses",
"Sample size and power", "Probability density", "The exponential distribution", "Some properties of the normal distribution",
"Holiday", "Method-of-moments estimates", "The bias-variance tradeoff", "Correlation", 
"Least squares linear prediction", "The regression effect and the regression fallacy", "Error in the regression estimate",
"Holiday", "Holiday", "The regression model for data", "Inference for the true slope in the regression model", "Conclusion"]


date = datetime.datetime(2019, 8, 26)
lectureCount = 0

for i in range(15):


  print("""
  - weekNum: {}
    weekName: {}
    weekDuration: {}-{}
    basic:
    - date: Mon {}
      content: "{}"  
      assignments:
      - name: {}    
    - date: Tues {}
      content: "{}"
    - date: Wed {}
      content: "{}"
    - date: Thu {}
      content: "{}"
    - date: Fri {}
      content: "{}"
  """.format(i+1, weekNames[i], date.strftime("%x")[:-3], (date + datetime.timedelta(days=4)).strftime("%x")[:-3],
    (date + datetime.timedelta(days=0)).strftime("%x")[:-3], getCompleteString(lectureTitles[i * 3]),
    getPossibleHomework(date),
    (date + datetime.timedelta(days=1)).strftime("%x")[:-3], getPossibleQuiz((date + datetime.timedelta(days=1)).strftime("%x")[:-3]),
    (date + datetime.timedelta(days=2)).strftime("%x")[:-3], getCompleteString(lectureTitles[i * 3 + 1]),
    (date + datetime.timedelta(days=3)).strftime("%x")[:-3], getPossibleQuiz((date + datetime.timedelta(days=3)).strftime("%x")[:-3]),
    (date + datetime.timedelta(days=4)).strftime("%x")[:-3], getCompleteString(lectureTitles[i * 3 + 2]) )
  )

  date += datetime.timedelta(days=7)

 
```
