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
