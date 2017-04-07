# JARCID
An automated version of JARCID.

Just A Rather Cool and Informative Dashboard to keep track of buildings in Ottawa and Gatineau with OpenStreetMap.

This is actually more than a dashboard: it is an automated analysis of OpenStreetMap data and a data product with R and RStudio. JARCID downloads provincial osm extracts, creates time stamps, subsets to cities then to buildings, analyses the data to produce desired estimates, creates maps and assembles everything into a dashboard to report. It requires no intervention. It is intended to run monthly but can be run at any time as the code allows for any inputs and will always look for the last entry.

JARCID could be changed to track anything in OSM and can also iteratively build a database.

This was developed to produce a time series from OSM data and monitor changes for the OSM Crowdsourcing buildings project at Statistics Canada.

## Dependencies

[Osmosis](http://wiki.openstreetmap.org/wiki/Osmosis) is used to process osm data in the first phase. Installation instructions can be found [here](http://wiki.openstreetmap.org/wiki/Osmosis#How_to_install).

JARCID is an R application using R code and R markdown. Get R from CRAN [here](https://cran.r-project.org/). RStudio is an interface to R and so much more. It provides a complete environment for R and other tools: [RStudio](https://www.rstudio.com/).

JARCID requires that some packages be installed but the code takes of care of that so there is no need to install them one by one.

## Instructions

JARCID will need an initial dataset to get started. A first run version will be updated in the repository to create the first dataset and the first map. After the first run, JARCID can take over every month. I will add instructions on how to adapt for different cities.

A directory OSMdata must be created in the same directory where the JARCID repo was cloned. I will make these instructions clearer.

JARCID sends commands to the terminal and Windows shell so there are two versions depending on the operating system.

The whole application is written in R markdown: the file index.Rmd. Rmd is for "R markdown". [Markdown](http://daringfireball.net/projects/markdown/)is a light weight markup language in plain text created by [John Gruber](http://daringfireball.net/) that can be converted to many formats. [R markdown](http://rmarkdown.rstudio.com/), is an R implementation of markdown. It is now a major framework to create reproducbile research and documentation in data science. More than that, it integrates the full spectrum from data collection and input to data product.

### Running manually
open index.Rmd in RStudio. Click "Knit". Jarcid requires about 2 hours depending on the environment.

### Running automatically
This depends on which OS version is used. The easy way is to install the packages [cronR](https://github.com/bnosac/cronR) (macOS) or [taskscheduleR](https://github.com/bnosac/taskscheduleR) (Windows). Then, by clicking the "Addins" button in RStudio, you will have access to the automation functions. It is recommmended to pick the monthly setting. 

To automate the "knitting" process of JARCID, a script should be given to taskscheduleR or cronR instead of the Rmd file 


