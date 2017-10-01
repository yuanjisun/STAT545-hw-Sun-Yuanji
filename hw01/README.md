# STAT 545A Homework Repo
This repo is for all STAT 545A homework.

## Homework 02
Homework 02 is stored in the folder hw02. [Here is the link to that folder](https://github.com/yuanjisun/STAT545-hw-Sun-Yuanji/tree/master/hw02)

There is brief introduction to this homework in the README file in that folder.


# _Yuanji_'s Homework 1 for **STAT 545A**

## Report Process
1. All files in Homework 1 are pulled, edited locally, saved, committed from RStudio and finally pushed to github.com (I am quite familiar with this). I did **NOT** edit any files in the browser at github.com.
2. [Link to the rendered .md for the Gapminder exploration](https://github.com/yuanjisun/STAT545-hw01-Sun-Yuanji/blob/master/hw01_gapminder.md)
[Website: https://github.com/yuanjisun/STAT545-hw01-Sun-Yuanji/blob/master/hw01_gapminder.md]
3. The R Markdown works properly just as expected. At the very beginning, I ran into an error when render the file. This is because I used "github_document" and "keep_md: yes" at the same time. After removing "keep_md: yes", the .md file was created automatically and everything went on very well.
4. For the time, all tasks are quite straight forward and easy to be finished. I find that Use R! series by Springer and R for Data Science by O'Reilly are quite helpful for me in mastering R programming.


## Homework 1
Hello STAT 545Aers :wink: ! Welcome to my first homework for this great course. This homework is divided into the following two parts, self-introduction and Markdown skill practice :blush: .


### Part 1. Self-introduction
My name is **Yuanji Sun**, a graduate student in the _Department of Earth, Ocean and Atmospheric Sciences_ starting from _January 2017_ (so I am still "new" now) :relaxed: . I am studying both chemical oceanography and biological oceanography with a special focus on the biogeochemical behavior of organic contaminants, such as _PCBs_ and _PBDEs_. Due to the nature of my research, I have cruises from time to time.

Before coming to UBC, I received a B.S. degree in **Environmental Science** in China, during which time my research involved the biogeochemical cycling of N and P in lakes, as well as OCPs in sediments.

Want to know more about me? [Click here to see my profile on LinkedIn](https://www.linkedin.com/in/yuanjisun/)

Here is my contact information.

- Email: ysun@eoas.ubc.ca
- Office phone number: (+1) 604-822-2936
- Twitter: @yuanjisun

![The University of British Columbia](https://images.forbes.com/media/lists/companies/university-of-british-columbia_416x416.jpg)


### Part 2. Markdown Skill Practice
This part is designed to demonstrate that I have mastered several skills in Markdown coding. Thus, the content itself may not be interesting. Several skills are applied, including

1. H1~H4 Headers
2. **Bold** and _Italics_
3. Links
4. Bullets
5. Numbered List
6. Quoting Quotables
7. Citing Code
8. Emoji/Status
9. Images

#### 1. Headers
As is shown above, H1~H3 headers are used in this file.

#### 2. **Bold** and _Italics_
As is shown above, **Bold** and _Italics_ are used.

#### 3. Links
[Link to main STAT 545A webpage](http://stat545.com/)
The link to my profile can be found in the self-introduction above.

#### 4. Bullets
Here is an example with different shapes of bullets in three levels, which are also used above.

* Bullet 1
* Bullet 2
	+ Bullet 2.1
		* Bullet 2.1.1
* Bullet 3

#### 5. Numbered List
Just as an example, which is also used above.

1. Number One
2. Number Two
3. Number Three

#### 6. Quoting Quotables
I am glad to give you a brief introduction of Oceanography at UBC.

> Our more than 60 oceanography faculty, staff, postdocs, and graduate students direct their work at both solving practical problems and pursuing scientific discovery in the oceans. The Strait of Georgia and Salish Sea provide natural oceanographic laboratories in our backyard, but we also work in the Arctic, Antarctic and all other oceans in between. Our department has a wealth of analytical facilities to support this work, including the world-renowned Pacific Center for Isotopic and Geochemical Research (PCIGR).

#### 7. Citing Code
Here is a sample code made by myself on 03-Sep-2017. Please do **NOT** publish it. Since you do not have raw data, the code below could not be run properly.

This code is used to find the correlation between sulfate and nitrate in the atmosphere. First, I changed the working directory. Second, I combined the string so that the file can be located and opened. Third, select the data I want (skip NA). Finally, do simple calculations.

```R
all <- complete("specdata")
corr <- function(specdata, threshold = 0) {
        specdata <- "C:/Users/yuanj/Desktop/specdata"
        setwd(specdata)
        correlation <- c()
        all_id <- unlist(all$id)
        calculation <- c()
        for (id in all_id) {
                if (unclass(all$nobs[id])>threshold) {
                        if (id < 10) {
                                doc_name <- paste("00", id, ".csv", sep="")
                                data <- read.csv(doc_name)
                                sulfate <- c()
                                nitrate <- c()
                                for (x in 1:nrow(data)) {
                                        if (!is.na(data$sulfate[x]) & !is.na(data$nitrate[x])) {
                                                sulfate <- rbind(sulfate, unclass(data$sulfate[x]))
                                                nitrate <- rbind(nitrate, unclass(data$nitrate[x]))
                                        }
                                }
                                calculation <- rbind (calculation, cor(unclass(sulfate),unclass(nitrate)))
                        } else if (id < 100) {
                                doc_name <- paste("0", id, ".csv", sep="")
                                data <- read.csv(doc_name)
                                sulfate <- c()
                                nitrate <- c()
                                for (x in 1:nrow(data)) {
                                        if (!is.na(data$sulfate[x]) & !is.na(data$nitrate[x])) {
                                                sulfate <- rbind(sulfate, unclass(data$sulfate[x]))
                                                nitrate <- rbind(nitrate, unclass(data$nitrate[x]))
                                        }
                                }
                                calculation <- rbind (calculation, cor(unclass(sulfate),unclass(nitrate)))
                        } else {
                                doc_name <- paste(id, ".csv", sep="")
                                data <- read.csv(doc_name)
                                sulfate <- c()
                                nitrate <- c()
                                for (x in 1:nrow(data)) {
                                        if (!is.na(data$sulfate[x]) & !is.na(data$nitrate[x])) {
                                                sulfate <- rbind(sulfate, unclass(data$sulfate[x]))
                                                nitrate <- rbind(nitrate, unclass(data$nitrate[x]))
                                        }
                                }
                                calculation <- rbind (calculation, cor(unclass(sulfate),unclass(nitrate)))
                        }
                }
        }
      unclass(calculation)
}
```

#### 8. Emoji/Status
Several emoji are used above.

#### 9. Image
Please see the UBC logo above.

[This is the end of README.md :blush:]
