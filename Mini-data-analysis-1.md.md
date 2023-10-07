Mini Data-Analysis Deliverable 1
================

# Welcome to your (maybe) first-ever data analysis project!

And hopefully the first of many. Let’s get started:

1.  Install the [`datateachr`](https://github.com/UBC-MDS/datateachr)
    package by typing the following into your **R terminal**:

<!-- -->

``` r
    install.packages("devtools")
```

    ## Error in install.packages : Updating loaded packages

``` r
    devtools::install_github("UBC-MDS/datateachr")
```

    ## Skipping install of 'datateachr' from a github remote, the SHA1 (78d391f4) has not changed since last install.
    ##   Use `force = TRUE` to force installation

    install.packages("devtools")
    devtools::install_github("UBC-MDS/datateachr")

2.  Load the packages below.

``` r
library(datateachr)
library(tidyverse)
```

3.  Make a repository in the <https://github.com/stat545ubc-2023>
    Organization. You can do this by following the steps found on canvas
    in the entry called [MDA: Create a
    repository](https://canvas.ubc.ca/courses/126199/pages/mda-create-a-repository).
    One completed, your repository should automatically be listed as
    part of the stat545ubc-2023 Organization.

# Instructions

## For Both Milestones

- Each milestone has explicit tasks. Tasks that are more challenging
  will often be allocated more points.

- Each milestone will be also graded for reproducibility, cleanliness,
  and coherence of the overall Github submission.

- While the two milestones will be submitted as independent
  deliverables, the analysis itself is a continuum - think of it as two
  chapters to a story. Each chapter, or in this case, portion of your
  analysis, should be easily followed through by someone unfamiliar with
  the content.
  [Here](https://swcarpentry.github.io/r-novice-inflammation/06-best-practices-R/)
  is a good resource for what constitutes “good code”. Learning good
  coding practices early in your career will save you hassle later on!

- The milestones will be equally weighted.

## For Milestone 1

**To complete this milestone**, edit [this very `.Rmd`
file](https://raw.githubusercontent.com/UBC-STAT/stat545.stat.ubc.ca/master/content/mini-project/mini-project-1.Rmd)
directly. Fill in the sections that are tagged with
`<!--- start your work below --->`.

**To submit this milestone**, make sure to knit this `.Rmd` file to an
`.md` file by changing the YAML output settings from
`output: html_document` to `output: github_document`. Commit and push
all of your work to the mini-analysis GitHub repository you made
earlier, and tag a release on GitHub. Then, submit a link to your tagged
release on canvas.

**Points**: This milestone is worth 36 points: 30 for your analysis, and
6 for overall reproducibility, cleanliness, and coherence of the Github
submission.

# Learning Objectives

By the end of this milestone, you should:

- Become familiar with your dataset of choosing
- Select 4 questions that you would like to answer with your data
- Generate a reproducible and clear report using R Markdown
- Become familiar with manipulating and summarizing your data in tibbles
  using `dplyr`, with a research question in mind.

# Task 1: Choose your favorite dataset

The `datateachr` package by Hayley Boyce and Jordan Bourak currently
composed of 7 semi-tidy datasets for educational purposes. Here is a
brief description of each dataset:

- *apt_buildings*: Acquired courtesy of The City of Toronto’s Open Data
  Portal. It currently has 3455 rows and 37 columns.

- *building_permits*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 20680 rows and 14 columns.

- *cancer_sample*: Acquired courtesy of UCI Machine Learning Repository.
  It currently has 569 rows and 32 columns.

- *flow_sample*: Acquired courtesy of The Government of Canada’s
  Historical Hydrometric Database. It currently has 218 rows and 7
  columns.

- *parking_meters*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 10032 rows and 22 columns.

- *steam_games*: Acquired courtesy of Kaggle. It currently has 40833
  rows and 21 columns.

- *vancouver_trees*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 146611 rows and 20 columns.

**Things to keep in mind**

- We hope that this project will serve as practice for carrying our your
  own *independent* data analysis. Remember to comment your code, be
  explicit about what you are doing, and write notes in this markdown
  document when you feel that context is required. As you advance in the
  project, prompts and hints to do this will be diminished - it’ll be up
  to you!

- Before choosing a dataset, you should always keep in mind **your
  goal**, or in other ways, *what you wish to achieve with this data*.
  This mini data-analysis project focuses on *data wrangling*,
  *tidying*, and *visualization*. In short, it’s a way for you to get
  your feet wet with exploring data on your own.

And that is exactly the first thing that you will do!

1.1 **(1 point)** Out of the 7 datasets available in the `datateachr`
package, choose **4** that appeal to you based on their description.
Write your choices below:

**Note**: We encourage you to use the ones in the `datateachr` package,
but if you have a dataset that you’d really like to use, you can include
it here. But, please check with a member of the teaching team to see
whether the dataset is of appropriate complexity. Also, include a
**brief** description of the dataset here to help the teaching team
understand your data.

<!-------------------------- Start your work below ---------------------------->

1: *apt_buildings* 2: *vancouver_trees* 3: *parking_meters* 4:
*steam_games*

<!----------------------------------------------------------------------------->

1.2 **(6 points)** One way to narrowing down your selection is to
*explore* the datasets. Use your knowledge of dplyr to find out at least
*3* attributes about each of these datasets (an attribute is something
such as number of rows, variables, class type…). The goal here is to
have an idea of *what the data looks like*.

*Hint:* This is one of those times when you should think about the
cleanliness of your analysis. I added a single code chunk for you below,
but do you want to use more than one? Would you like to write more
comments outside of the code chunk?

<!-------------------------- Start your work below ---------------------------->

``` r
#Attributes for "stream_games" dataset
glimpse(steam_games)
```

    ## Rows: 40,833
    ## Columns: 21
    ## $ id                       [3m[38;5;246m<dbl>[39m[23m 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53,…
    ## $ url                      [3m[38;5;246m<chr>[39m[23m "https://store.steampowered.com/app/379720/DOOM/", "https://store.steampowered.com/app/578080/PLAYERUNKNOWNS_BATTLEGROUNDS/", "https://store.steampowered.com/app/637090/BATTLETECH/", "https://store.stea…
    ## $ types                    [3m[38;5;246m<chr>[39m[23m "app", "app", "app", "app", "app", "bundle", "app", "app", "app", "app", "app", "app", "app", "app", "app", "bundle", "app", "app", "app", "app", "app", "app", "app", "app", "app", "bundle", "app", "app…
    ## $ name                     [3m[38;5;246m<chr>[39m[23m "DOOM", "PLAYERUNKNOWN'S BATTLEGROUNDS", "BATTLETECH", "DayZ", "EVE Online", "Grand Theft Auto V: Premium Online Edition", "Devil May Cry 5", "Human: Fall Flat", "They Are Billions", "Warhammer: Chaosba…
    ## $ desc_snippet             [3m[38;5;246m<chr>[39m[23m "Now includes all three premium DLC packs (Unto the Evil, Hell Followed, and Bloodfall), maps, modes, and weapons, as well as all feature updates including Arcade Mode, Photo Mode, and the latest Update…
    ## $ recent_reviews           [3m[38;5;246m<chr>[39m[23m "Very Positive,(554),- 89% of the 554 user reviews in the last 30 days are positive.", "Mixed,(6,214),- 49% of the 6,214 user reviews in the last 30 days are positive.", "Mixed,(166),- 54% of the 166 us…
    ## $ all_reviews              [3m[38;5;246m<chr>[39m[23m "Very Positive,(42,550),- 92% of the 42,550 user reviews for this game are positive.", "Mixed,(836,608),- 49% of the 836,608 user reviews for this game are positive.", "Mostly Positive,(7,030),- 71% of …
    ## $ release_date             [3m[38;5;246m<chr>[39m[23m "May 12, 2016", "Dec 21, 2017", "Apr 24, 2018", "Dec 13, 2018", "May 6, 2003", "NaN", "Mar 7, 2019", "Jul 22, 2016", "Dec 12, 2017", "May 31, 2019", "Apr 19, 2018", "Sep 25, 2017", "May 5, 2015", "Jul 2…
    ## $ developer                [3m[38;5;246m<chr>[39m[23m "id Software", "PUBG Corporation", "Harebrained Schemes", "Bohemia Interactive", "CCP", "Rockstar North", "CAPCOM Co., Ltd.", "No Brakes Games", "Numantian Games", "Eko Software", "IronOak Games", "Spik…
    ## $ publisher                [3m[38;5;246m<chr>[39m[23m "Bethesda Softworks,Bethesda Softworks", "PUBG Corporation,PUBG Corporation", "Paradox Interactive,Paradox Interactive", "Bohemia Interactive,Bohemia Interactive", "CCP,CCP", "Rockstar Games", "CAPCOM C…
    ## $ popular_tags             [3m[38;5;246m<chr>[39m[23m "FPS,Gore,Action,Demons,Shooter,First-Person,Great Soundtrack,Multiplayer,Singleplayer,Fast-Paced,Sci-fi,Horror,Classic,Atmospheric,Difficult,Blood,Remake,Zombies,Co-op,Memes", "Survival,Shooter,Multipl…
    ## $ game_details             [3m[38;5;246m<chr>[39m[23m "Single-player,Multi-player,Co-op,Steam Achievements,Steam Trading Cards,Partial Controller Support,Steam Cloud", "Multi-player,Online Multi-Player,Stats", "Single-player,Multi-player,Online Multi-Playe…
    ## $ languages                [3m[38;5;246m<chr>[39m[23m "English,French,Italian,German,Spanish - Spain,Japanese,Polish,Portuguese - Brazil,Russian,Traditional Chinese", "English,Korean,Simplified Chinese,French,German,Spanish - Spain,Arabic,Japanese,Polish,P…
    ## $ achievements             [3m[38;5;246m<dbl>[39m[23m 54, 37, 128, NA, NA, NA, 51, 55, 34, 43, 72, 41, NA, 50, NA, NA, 12, 32, NA, 75, 68, 30, 51, 96, NA, NA, 15, 85, NA, 63, NA, 14, 47, 55, 58, NA, NA, 46, 61, NA, 77, 31, 147, 71, NA, 12, NA, 30, 45, 20, …
    ## $ genre                    [3m[38;5;246m<chr>[39m[23m "Action", "Action,Adventure,Massively Multiplayer", "Action,Adventure,Strategy", "Action,Adventure,Massively Multiplayer", "Action,Free to Play,Massively Multiplayer,RPG,Strategy", "Action,Adventure", "…
    ## $ game_description         [3m[38;5;246m<chr>[39m[23m "About This Game Developed by id software, the studio that pioneered the first-person shooter genre and created multiplayer Deathmatch, DOOM returns as a brutally fun and challenging modern-day shooter …
    ## $ mature_content           [3m[38;5;246m<chr>[39m[23m NA, "Mature Content Description  The developers describe the content like this:  This Game may contain content not appropriate for all ages, or may not be appropriate for viewing at work: Frequent Viole…
    ## $ minimum_requirements     [3m[38;5;246m<chr>[39m[23m "Minimum:,OS:,Windows 7/8.1/10 (64-bit versions),Processor:,Intel Core i5-2400/AMD FX-8320 or better,Memory:,8 GB RAM,Graphics:,NVIDIA GTX 670 2GB/AMD Radeon HD 7870 2GB or better,Storage:,55 GB availab…
    ## $ recommended_requirements [3m[38;5;246m<chr>[39m[23m "Recommended:,OS:,Windows 7/8.1/10 (64-bit versions),Processor:,Intel Core i7-3770/AMD FX-8350 or better,Memory:,8 GB RAM,Graphics:,NVIDIA GTX 970 4GB/AMD Radeon R9 290 4GB or better,Storage:,55 GB avai…
    ## $ original_price           [3m[38;5;246m<dbl>[39m[23m 19.99, 29.99, 39.99, 44.99, 0.00, NA, 59.99, 14.99, 29.99, 49.99, 19.99, 39.99, 0.00, 1.02, 19.99, NA, 14.99, 59.99, 0.00, 19.99, 1.02, 29.99, 39.99, 19.99, 19.99, NA, 9.99, 12.99, 57.91, 59.99, 0.00, 2…
    ## $ discount_price           [3m[38;5;246m<dbl>[39m[23m 14.99, NA, NA, NA, NA, 35.18, 70.42, 17.58, NA, NA, NA, 59.97, NA, 906.48, NA, 94.45, NA, NA, NA, 122.31, 906.48, 38.25, NA, 54.97, NA, 14.98, 14.98, 39.71, 46.26, NA, NA, 32.38, 59.97, NA, 46.77, 225.3…

``` r
#Attributes for "parking_meters" dataset
glimpse(parking_meters)
```

    ## Rows: 10,032
    ## Columns: 22
    ## $ meter_head     [3m[38;5;246m<chr>[39m[23m "Twin", "Pay Station", "Twin", "Single", "Twin", "Twin", "Twin", "Single", "Twin", "Twin", "Twin", "Twin", "Twin", "Twin", "Pay Station", "Single / Disability", "Twin", "Twin", "Twin", "Twin", "Twin", "Twin", "Tw…
    ## $ r_mf_9a_6p     [3m[38;5;246m<chr>[39m[23m "$2.00", "$1.00", "$1.00", "$1.00", "$2.00", "$2.00", "$2.00", "$2.00", "$4.00", "$2.00", "$2.00", "$2.00", "$2.00", "$1.00", "$1.00", "$4.00", "$4.00", "$4.00", "$4.00", "$1.00", "$5.00", "$2.00", "$3.00", "$3.0…
    ## $ r_mf_6p_10     [3m[38;5;246m<chr>[39m[23m "$4.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "$3.00", "$3.00", "$1.00", "$1.00", "$1.00", "$1.00", "$4.00", "$2.00", "$1.00", "$3.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "$2.00", "$1.0…
    ## $ r_sa_9a_6p     [3m[38;5;246m<chr>[39m[23m "$2.00", "$1.00", "$1.00", "$1.00", "$2.00", "$2.00", "$2.00", "$2.00", "$4.00", "$2.00", "$2.00", "$2.00", "$2.00", "$1.00", "$1.00", "$4.00", "$4.00", "$4.00", "$4.00", "$1.00", "$5.00", "$2.00", "$3.00", "$3.0…
    ## $ r_sa_6p_10     [3m[38;5;246m<chr>[39m[23m "$4.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "$3.00", "$3.00", "$1.00", "$1.00", "$1.00", "$1.00", "$4.00", "$2.00", "$1.00", "$3.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "$2.00", "$1.0…
    ## $ r_su_9a_6p     [3m[38;5;246m<chr>[39m[23m "$2.00", "$1.00", "$1.00", "$1.00", "$2.00", "$2.00", "$2.00", "$2.00", "$4.00", "$2.00", "$2.00", "$2.00", "$2.00", "$1.00", "$1.00", "$4.00", "$4.00", "$4.00", "$4.00", "$1.00", "$5.00", "$2.00", "$3.00", "$3.0…
    ## $ r_su_6p_10     [3m[38;5;246m<chr>[39m[23m "$4.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "$3.00", "$3.00", "$1.00", "$1.00", "$1.00", "$1.00", "$4.00", "$2.00", "$1.00", "$3.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "$2.00", "$1.0…
    ## $ rate_misc      [3m[38;5;246m<chr>[39m[23m NA, "$ .50", NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, "$ .50", NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, "$…
    ## $ time_in_effect [3m[38;5;246m<chr>[39m[23m "METER IN EFFECT: 9:00 AM TO 10:00 PM", "METER IN EFFECT: 9:00 AM TO 10:00 PM", "METER IN EFFECT: 9:00 AM TO 10:00 PM", "METER IN EFFECT: 9:00 AM TO 10:00 PM", "METER IN EFFECT: 9:00 AM TO 10:00 PM", "METER IN EF…
    ## $ t_mf_9a_6p     [3m[38;5;246m<chr>[39m[23m "2 Hr", "10 Hrs", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "3 Hr", "3 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2…
    ## $ t_mf_6p_10     [3m[38;5;246m<chr>[39m[23m "4 Hr", "10 Hrs", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4…
    ## $ t_sa_9a_6p     [3m[38;5;246m<chr>[39m[23m "2 Hr", "10 Hrs", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "3 Hr", "3 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2…
    ## $ t_sa_6p_10     [3m[38;5;246m<chr>[39m[23m "4 Hr", "10 Hrs", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4…
    ## $ t_su_9a_6p     [3m[38;5;246m<chr>[39m[23m "2 Hr", "10 Hrs", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "3 Hr", "3 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2 Hr", "2…
    ## $ t_su_6p_10     [3m[38;5;246m<chr>[39m[23m "4 Hr", "10 Hrs", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4…
    ## $ time_misc      [3m[38;5;246m<chr>[39m[23m NA, "No Time Limit", NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, "13 Hrs", NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, N…
    ## $ credit_card    [3m[38;5;246m<chr>[39m[23m "No", "Yes", "No", "No", "No", "No", "No", "No", "No", "No", "No", "No", "Yes", "No", "Yes", "No", "No", "No", "No", "No", "No", "No", "No", "No", "No", "No", "No", "No", "No", "No", "No", "No", "No", "No", "Yes"…
    ## $ pay_phone      [3m[38;5;246m<chr>[39m[23m "66890", "59916", "57042", "57159", "51104", "60868", "60810", "60577", "52884", "66822", "66848", "66815", "66219", "52340", "59929", "54667", "50212", "51700", "51728", "52409", "52743", "52441", "65877", "5420…
    ## $ longitude      [3m[38;5;246m<dbl>[39m[23m -123.1289, -123.0982, -123.1013, -123.1862, -123.1278, -123.1265, -123.1197, -123.1198, -123.1389, -123.1271, -123.1269, -123.1270, -123.1249, -123.1153, -123.1003, -123.1476, -123.1313, -123.1313, -123.1314, -12…
    ## $ latitude       [3m[38;5;246m<dbl>[39m[23m 49.28690, 49.27215, 49.25468, 49.26341, 49.26354, 49.27431, 49.27771, 49.27763, 49.26540, 49.27394, 49.27406, 49.27400, 49.28443, 49.25526, 49.25485, 49.27063, 49.26384, 49.26373, 49.26387, 49.26443, 49.26338, 49…
    ## $ geo_local_area [3m[38;5;246m<chr>[39m[23m "West End", "Strathcona", "Riley Park", "West Point Grey", "Fairview", "Downtown", "Downtown", "Downtown", "Fairview", "Downtown", "Downtown", "Downtown", "West End", "South Cambie", "Riley Park", "Kitsilano", "F…
    ## $ meter_id       [3m[38;5;246m<chr>[39m[23m "670805", "471405", "C80145", "D03704", "301023", "591318", "580933", "580935", "B71501", "591340", "591330", "591334", "650802", "563317", "C80209", "B11842", "862410", "862414", "862409", "B81129", "300625", "3…

``` r
#Attributes for "vancouver_trees" dataset
glimpse(vancouver_trees)
```

    ## Rows: 146,611
    ## Columns: 20
    ## $ tree_id            [3m[38;5;246m<dbl>[39m[23m 149556, 149563, 149579, 149590, 149604, 149616, 149617, 149618, 149619, 149625, 149626, 149636, 149640, 149646, 149647, 149658, 149673, 149680, 149683, 149684, 149686, 149694, 155226, 155243, 155251, 155293, …
    ## $ civic_number       [3m[38;5;246m<dbl>[39m[23m 494, 450, 4994, 858, 5032, 585, 4909, 4925, 4969, 720, 736, 812, 6968, 505, 509, 5208, 5241, 5311, 7011, 1223, 5007, 1292, 4525, 501, 4099, 665, 6510, 6626, 316, 319, 501, 501, 2408, 1451, 1451, 1900, 814, 81…
    ## $ std_street         [3m[38;5;246m<chr>[39m[23m "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV", "WINDSOR ST", "W 61ST AV", "SHERBROOKE ST", "SHERBROOKE ST", "SHERBROOKE ST", "E 39TH AV", "E 39TH AV", "E 39TH AV", "SELKIRK ST", "E 16TH AV", "E 16TH AV"…
    ## $ genus_name         [3m[38;5;246m<chr>[39m[23m "ULMUS", "ZELKOVA", "STYRAX", "FRAXINUS", "ACER", "PYRUS", "ACER", "ACER", "ACER", "FRAXINUS", "TILIA", "TILIA", "ACER", "HIBISCUS", "STYRAX", "STYRAX", "FRAXINUS", "ACER", "ACER", "ACER", "ACER", "ACER", "LI…
    ## $ species_name       [3m[38;5;246m<chr>[39m[23m "AMERICANA", "SERRATA", "JAPONICA", "AMERICANA", "CAMPESTRE", "CALLERYANA", "PLATANOIDES", "PLATANOIDES", "PLATANOIDES", "AMERICANA", "EUCHLORA   X", "EUCHLORA   X", "PLATANOIDES", "SYRIACA", "JAPONICA", "JAP…
    ## $ cultivar_name      [3m[38;5;246m<chr>[39m[23m "BRANDON", NA, NA, "AUTUMN APPLAUSE", NA, "CHANTICLEER", "COLUMNARE", "COLUMNARE", "COLUMNARE", "AUTUMN APPLAUSE", NA, NA, "COLUMNARE", NA, NA, NA, "RAYWOOD", NA, "COLUMNARE", "COLUMNARE", NA, "COLUMNARE", NA…
    ## $ common_name        [3m[38;5;246m<chr>[39m[23m "BRANDON ELM", "JAPANESE ZELKOVA", "JAPANESE SNOWBELL", "AUTUMN APPLAUSE ASH", "HEDGE MAPLE", "CHANTICLEER PEAR", "COLUMNAR NORWAY MAPLE", "COLUMNAR NORWAY MAPLE", "COLUMNAR NORWAY MAPLE", "AUTUMN APPLAUSE AS…
    ## $ assigned           [3m[38;5;246m<chr>[39m[23m "N", "N", "N", "Y", "N", "N", "N", "N", "N", "N", "N", "Y", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "Y", "Y", "N", "N", "N", "N", "N", "Y", "Y", "N", "Y", "Y", "N", "N", "N", "N", "N", "N", "N"…
    ## $ root_barrier       [3m[38;5;246m<chr>[39m[23m "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "N"…
    ## $ plant_area         [3m[38;5;246m<chr>[39m[23m "N", "N", "4", "4", "4", "B", "6", "6", "3", "3", "5", "3", "N", "3", "2", "4", "4", "4", "N", "N", "3", "N", "N", NA, NA, NA, "10", "10", "C", "C", NA, NA, "10", "B", "B", "7", "4", "4", NA, NA, "8", "7", "8…
    ## $ on_street_block    [3m[38;5;246m<dbl>[39m[23m 400, 400, 4900, 800, 5000, 500, 4900, 4900, 4900, 700, 700, 800, 6900, 500, 500, 5200, 5200, 5300, 7000, 7000, 5000, 6500, 4500, 4000, 4000, 600, 6500, 6600, 300, 300, 4000, 4000, 3400, 1400, 1400, 1900, 800,…
    ## $ on_street          [3m[38;5;246m<chr>[39m[23m "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV", "WINDSOR ST", "W 61ST AV", "SHERBROOKE ST", "SHERBROOKE ST", "SHERBROOKE ST", "E 39TH AV", "E 39TH AV", "E 39TH AV", "SELKIRK ST", "E 16TH AV", "E 16TH AV"…
    ## $ neighbourhood_name [3m[38;5;246m<chr>[39m[23m "MARPOLE", "MARPOLE", "KENSINGTON-CEDAR COTTAGE", "KENSINGTON-CEDAR COTTAGE", "KENSINGTON-CEDAR COTTAGE", "MARPOLE", "KENSINGTON-CEDAR COTTAGE", "KENSINGTON-CEDAR COTTAGE", "KENSINGTON-CEDAR COTTAGE", "KENSIN…
    ## $ street_side_name   [3m[38;5;246m<chr>[39m[23m "EVEN", "EVEN", "EVEN", "EVEN", "EVEN", "ODD", "ODD", "ODD", "ODD", "EVEN", "EVEN", "EVEN", "EVEN", "ODD", "ODD", "EVEN", "ODD", "ODD", "ODD", "ODD", "ODD", "EVEN", "ODD", "EVEN", "ODD", "ODD", "EVEN", "EVEN"…
    ## $ height_range_id    [3m[38;5;246m<dbl>[39m[23m 2, 4, 3, 4, 2, 2, 3, 3, 2, 2, 2, 5, 3, 2, 2, 2, 2, 2, 3, 2, 2, 3, 2, 2, 2, 4, 4, 4, 3, 5, 2, 2, 2, 3, 3, 1, 3, 3, 2, 3, 2, 4, 2, 1, 2, 2, 2, 2, 4, 4, 4, 3, 4, 3, 2, 3, 6, 3, 3, 3, 2, 3, 2, 4, 4, 1, 2, 2, 2, 2…
    ## $ diameter           [3m[38;5;246m<dbl>[39m[23m 10.00, 10.00, 4.00, 18.00, 9.00, 5.00, 15.00, 14.00, 16.00, 7.50, 7.75, 16.00, 18.00, 4.50, 8.00, 4.00, 14.00, 10.25, 19.50, 14.00, 9.75, 13.50, 3.00, 17.00, 9.00, 14.00, 13.00, 11.50, 15.00, 15.75, 16.00, 9.…
    ## $ curb               [3m[38;5;246m<chr>[39m[23m "N", "N", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "N", "N", "N", "N", "Y", "Y", "N", "N", "Y", "Y"…
    ## $ date_planted       [3m[38;5;246m<date>[39m[23m 1999-01-13, 1996-05-31, 1993-11-22, 1996-04-29, 1993-12-17, NA, 1993-12-16, 1993-12-16, 1993-12-16, 1993-12-03, 1993-12-03, 1993-12-03, 1993-12-15, 1993-11-19, 1993-11-19, 1993-12-21, 1993-12-20, 1993-12-20,…
    ## $ longitude          [3m[38;5;246m<dbl>[39m[23m -123.1161, -123.1147, -123.0846, -123.0870, -123.0846, -123.1196, -123.0813, -123.0813, -123.0813, -123.0897, -123.0896, -123.0877, -123.1334, -123.0932, -123.0930, -123.0846, -123.0847, -123.0848, -123.1335,…
    ## $ latitude           [3m[38;5;246m<dbl>[39m[23m 49.21776, 49.21776, 49.23938, 49.23469, 49.23894, 49.21513, 49.23998, 49.23972, 49.23951, 49.23472, 49.23472, 49.23470, 49.22311, 49.25654, 49.25653, 49.23778, 49.23751, 49.23680, 49.22274, 49.22200, 49.23922…

``` r
#Attributes for "apt_buildings" dataset
glimpse(apt_buildings)
```

    ## Rows: 3,455
    ## Columns: 37
    ## $ id                               [3m[38;5;246m<dbl>[39m[23m 10359, 10360, 10361, 10362, 10363, 10364, 10365, 10366, 10367, 10368, 10369, 10370, 10371, 10372, 10373, 10374, 10375, 10376, 10377, 10378, 10379, 10380, 10381, 10382, 10383, 10384, 10385, 10386…
    ## $ air_conditioning                 [3m[38;5;246m<chr>[39m[23m "NONE", "NONE", "NONE", "NONE", "NONE", "NONE", "NONE", "CENTRAL AIR", "NONE", "NONE", "NONE", "NONE", "NONE", "NONE", "NONE", "NONE", "NONE", "NONE", "CENTRAL AIR", "NONE", "NONE", "NONE", "NON…
    ## $ amenities                        [3m[38;5;246m<chr>[39m[23m "Outdoor rec facilities", "Outdoor pool", NA, NA, NA, NA, NA, "Indoor pool , Indoor recreation room , Indoor exercise room", NA, "Indoor recreation room", NA, NA, NA, NA, "Indoor recreation room…
    ## $ balconies                        [3m[38;5;246m<chr>[39m[23m "YES", "YES", "YES", "YES", "NO", "NO", "NO", "YES", "YES", "YES", "NO", "YES", "YES", "YES", "YES", "NO", "YES", "NO", "YES", "YES", "YES", "NO", "YES", "NO", "YES", "YES", "YES", "YES", "YES",…
    ## $ barrier_free_accessibilty_entr   [3m[38;5;246m<chr>[39m[23m "YES", "NO", "NO", "YES", "NO", "NO", "YES", "NO", "YES", "YES", "YES", "NO", "YES", "NO", "NO", "NO", "YES", "NO", "YES", "NO", "NO", "NO", "NO", NA, "NO", "YES", "YES", "NO", "YES", "YES", "YE…
    ## $ bike_parking                     [3m[38;5;246m<chr>[39m[23m "0 indoor parking spots and 10 outdoor parking spots", "0 indoor parking spots and 34 outdoor parking spots", "Not Available", "Not Available", "12 indoor parking spots and 0 outdoor parking spo…
    ## $ exterior_fire_escape             [3m[38;5;246m<chr>[39m[23m "NO", "NO", "NO", "YES", "NO", NA, "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "YES", "NO", "NO", "NO", "YES", "NO", "NO", NA, "NO", "YES", "NO", "NO", "NO", "NO", "NO", "NO", "N…
    ## $ fire_alarm                       [3m[38;5;246m<chr>[39m[23m "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES"…
    ## $ garbage_chutes                   [3m[38;5;246m<chr>[39m[23m "YES", "YES", "NO", "NO", "NO", "NO", "NO", "YES", "YES", "NO", "NO", "YES", "NO", "NO", "NO", "NO", "YES", "NO", "YES", "NO", "YES", "NO", "YES", "NO", "YES", "YES", "YES", "YES", "YES", "NO", …
    ## $ heating_type                     [3m[38;5;246m<chr>[39m[23m "HOT WATER", "HOT WATER", "HOT WATER", "HOT WATER", "HOT WATER", "HOT WATER", "HOT WATER", "HOT WATER", "ELECTRIC", "HOT WATER", "HOT WATER", "HOT WATER", "HOT WATER", "HOT WATER", "HOT WATER", …
    ## $ intercom                         [3m[38;5;246m<chr>[39m[23m "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES"…
    ## $ laundry_room                     [3m[38;5;246m<chr>[39m[23m "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES"…
    ## $ locker_or_storage_room           [3m[38;5;246m<chr>[39m[23m "NO", "YES", "YES", "YES", "NO", "YES", "YES", "YES", "NO", "NO", "YES", "YES", "YES", "NO", "YES", "NO", "YES", "NO", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "NO", "NO", "YES", …
    ## $ no_of_elevators                  [3m[38;5;246m<dbl>[39m[23m 3, 3, 0, 1, 0, 0, 0, 2, 4, 2, 0, 2, 2, 1, 2, 0, 2, 0, 3, 1, 3, 0, 2, 0, 2, 2, 3, 2, 2, 2, 0, 0, 3, 2, 2, 3, 3, 2, 1, 0, 0, 0, 0, 3, 1, 0, 3, 2, 3, 1, 0, 3, 4, 0, 0, 1, 1, 1, 2, 2, 2, 3, 1, 2, 2,…
    ## $ parking_type                     [3m[38;5;246m<chr>[39m[23m "Underground Garage , Garage accessible thru buildg", "Underground Garage , Garage accessible thru buildg , Surface Parking", "Underground Garage , Garage accessible thru buildg , Surface Parkin…
    ## $ pets_allowed                     [3m[38;5;246m<chr>[39m[23m "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "NO", "YES", NA, "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "NO", "YES", "YE…
    ## $ prop_management_company_name     [3m[38;5;246m<chr>[39m[23m NA, "SCHICKEDANZ BROS. PROPERTIES", NA, "FREIMAN INVESTMENTS", NA, "GILINDO MARCOCCHIO LIMITED", "REALSTAR", "PRINCESS MANAGEMENT", NA, NA, NA, "WALL REAL ESTATE", "SIGNET GROUP INC", "GLOBAL PR…
    ## $ property_type                    [3m[38;5;246m<chr>[39m[23m "PRIVATE", "PRIVATE", "PRIVATE", "PRIVATE", "PRIVATE", "PRIVATE", "PRIVATE", "PRIVATE", "PRIVATE", "TCHC", "PRIVATE", "PRIVATE", "PRIVATE", "PRIVATE", "PRIVATE", "PRIVATE", "PRIVATE", "PRIVATE",…
    ## $ rsn                              [3m[38;5;246m<dbl>[39m[23m 4154812, 4154815, 4155295, 4155309, 4155318, 4155322, 4155325, 4155928, 4155952, 4155991, 4156004, 4152685, 4152689, 4152691, 4152694, 4154315, 4154331, 4154336, 4155675, 4155684, 4166732, 41541…
    ## $ separate_gas_meters              [3m[38;5;246m<chr>[39m[23m "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "N…
    ## $ separate_hydro_meters            [3m[38;5;246m<chr>[39m[23m "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "YES", "NO", "NO", "YES", "YES", "NO", "YES", "YES", "NO", "YES", "YES", "YES", "NO", "YES", "YES", "NO", "YES", "YES", "YES", "YES", "YES…
    ## $ separate_water_meters            [3m[38;5;246m<chr>[39m[23m "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "N…
    ## $ site_address                     [3m[38;5;246m<chr>[39m[23m "65  FOREST MANOR RD", "70  CLIPPER RD", "2651  BLOOR ST W", "22  BURNHAMTHORPE RD", "18  ANGLESEY BLVD", "308  THE KINGSWAY", "3  BEXHILL CRT", "41  WARRENDER AVE", "280  WELLESLEY ST E", "11  …
    ## $ sprinkler_system                 [3m[38;5;246m<chr>[39m[23m "YES", "YES", "NO", "YES", "NO", "NO", "NO", "YES", "YES", "YES", "NO", "YES", "YES", "NO", "YES", "NO", "YES", "NO", "YES", "YES", "YES", "NO", "YES", "NO", "YES", "YES", "YES", "YES", "YES", "…
    ## $ visitor_parking                  [3m[38;5;246m<chr>[39m[23m "PAID", "FREE", "UNAVAILABLE", "UNAVAILABLE", "UNAVAILABLE", "UNAVAILABLE", "PAID", "FREE", "PAID", "BOTH", "UNAVAILABLE", "BOTH", "FREE", "UNAVAILABLE", "FREE", "FREE", "FREE", "UNAVAILABLE", "…
    ## $ ward                             [3m[38;5;246m<chr>[39m[23m "17", "17", "03", "03", "02", "02", "02", "02", "13", "07", "09", "20", "20", "20", "21", "05", "05", "05", "17", "06", "17", "15", "08", "05", "05", "01", "19", "09", "06", "05", "11", "20", "1…
    ## $ window_type                      [3m[38;5;246m<chr>[39m[23m "DOUBLE PANE", "DOUBLE PANE", "DOUBLE PANE", "DOUBLE PANE", "DOUBLE PANE", "SINGLE PANE", "DOUBLE PANE", "SINGLE PANE", "DOUBLE PANE", "THERMAL", "DOUBLE PANE", "DOUBLE PANE", "DOUBLE PANE", "SI…
    ## $ year_built                       [3m[38;5;246m<dbl>[39m[23m 1967, 1970, 1927, 1959, 1943, 1952, 1959, 1971, 1969, 1972, 1945, 1968, 1959, 1958, 1960, 1958, 1960, 1955, 1971, 1964, 1965, 1947, 1960, 1952, 1973, 1971, 1994, 2005, 1967, 1969, 1992, 1971, 19…
    ## $ year_registered                  [3m[38;5;246m<dbl>[39m[23m 2017, 2017, 2017, 2017, 2017, NA, 2017, 2017, 2017, 2017, 2018, 2017, 2017, 2018, 2017, 2017, 2017, 2017, 2017, 2017, 2017, 2017, 2017, 2019, 2017, 2017, 2017, 2017, 2017, 2017, 2017, 2017, 2017…
    ## $ no_of_storeys                    [3m[38;5;246m<dbl>[39m[23m 17, 14, 4, 5, 4, 4, 4, 7, 32, 4, 4, 7, 5, 6, 7, 3, 10, 3, 12, 4, 18, 3, 7, 3, 15, 12, 6, 9, 8, 20, 3, 3, 19, 10, 10, 16, 21, 14, 4, 3, 4, 3, 3, 24, 4, 3, 13, 7, 19, 4, 3, 22, 30, 4, 4, 5, 7, 10,…
    ## $ emergency_power                  [3m[38;5;246m<chr>[39m[23m "NO", "YES", "NO", "NO", "NO", "NO", "NO", "YES", "NO", "YES", "YES", "NO", "NO", "NO", "YES", "NO", "NO", "NO", "YES", "NO", "NO", "NO", "YES", "YES", "NO", "YES", "YES", "YES", "NO", "YES", "N…
    ## $ `non-smoking_building`           [3m[38;5;246m<chr>[39m[23m "YES", "NO", "YES", "YES", "YES", "NO", "NO", "YES", "NO", "YES", "NO", "YES", "NO", "YES", "NO", "YES", "NO", "NO", "NO", "NO", "NO", "YES", "NO", NA, "YES", "YES", "NO", "YES", "NO", "NO", "YE…
    ## $ no_of_units                      [3m[38;5;246m<dbl>[39m[23m 218, 206, 34, 42, 25, 34, 14, 105, 571, 171, 26, 169, 87, 79, 71, 12, 105, 12, 235, 44, 287, 15, 61, 11, 146, 88, 106, 116, 77, 161, 17, 11, 244, 153, 117, 255, 237, 301, 39, 17, 25, 15, 22, 184…
    ## $ no_of_accessible_parking_spaces  [3m[38;5;246m<dbl>[39m[23m 8, 10, 20, 42, 12, 0, 5, 1, 1, 6, 12, 0, 1, NA, 2, 12, 4, 12, 0, 0, 2, 12, 0, NA, 0, 4, 2, 0, 1, 1, 17, 0, 5, 3, 2, 0, 1, 4, 0, 0, NA, 0, 22, 2, 0, 25, NA, 3, 1, 1, 0, 61, 1, 0, 0, 53, 0, 0, 0, …
    ## $ facilities_available             [3m[38;5;246m<chr>[39m[23m "Recycling bins", "Green Bin / Organics", "Green Bin / Organics", "Green Bin / Organics", "Green Bin / Organics", "Green Bin / Organics", "Unknown", "Green Bin / Organics", "Recycling bins", "Re…
    ## $ cooling_room                     [3m[38;5;246m<chr>[39m[23m "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "NO", "YES", "NO", "YES", "NO", "NO", "NO", "NO", "NO", "YES", "NO", "YES", "NO", "NO", "NO"…
    ## $ no_barrier_free_accessible_units [3m[38;5;246m<dbl>[39m[23m 2, 0, 0, 42, 0, NA, 14, 0, 0, 1, 25, 0, 0, NA, 0, 0, 0, 0, 235, 0, 0, 0, 0, NA, 0, 88, 4, 0, 77, 1, 5, 0, 0, 2, 2, 0, 0, 4, 0, 0, NA, 0, 0, 0, 0, 2, NA, 2, 8, 3, 0, 220, 0, 0, 0, 0, 0, 0, 0, 157…

<!----------------------------------------------------------------------------->

1.3 **(1 point)** Now that you’ve explored the 4 datasets that you were
initially most interested in, let’s narrow it down to 1. What lead you
to choose this one? Briefly explain your choice below.

<!-------------------------- Start your work below ---------------------------->

I chose the *apt_buildings*, which with highest number of columns (37)
of data and 2 class of variables (chr and dbl), could be quite
interesting to explore.

<!----------------------------------------------------------------------------->

1.4 **(2 points)** Time for a final decision! Going back to the
beginning, it’s important to have an *end goal* in mind. For example, if
I had chosen the `titanic` dataset for my project, I might’ve wanted to
explore the relationship between survival and other variables. Try to
think of 1 research question that you would want to answer with your
dataset. Note it down below.

<!-------------------------- Start your work below ---------------------------->

I chose the *apt_buildings* because I want to explore the relationship
between year_built and other variables (such as, \# of elevators,
storeys, units and etcetera), will the newer buildings have more
elevators/storeys/units number…?
<!----------------------------------------------------------------------------->

# Important note

Read Tasks 2 and 3 *fully* before starting to complete either of them.
Probably also a good point to grab a coffee to get ready for the fun
part!

This project is semi-guided, but meant to be *independent*. For this
reason, you will complete tasks 2 and 3 below (under the **START HERE**
mark) as if you were writing your own exploratory data analysis report,
and this guidance never existed! Feel free to add a brief introduction
section to your project, format the document with markdown syntax as you
deem appropriate, and structure the analysis as you deem appropriate. If
you feel lost, you can find a sample data analysis
[here](https://www.kaggle.com/headsortails/tidy-titarnic) to have a
better idea. However, bear in mind that it is **just an example** and
you will not be required to have that level of complexity in your
project.

# Task 2: Exploring your dataset

If we rewind and go back to the learning objectives, you’ll see that by
the end of this deliverable, you should have formulated *4* research
questions about your data that you may want to answer during your
project. However, it may be handy to do some more exploration on your
dataset of choice before creating these questions - by looking at the
data, you may get more ideas. **Before you start this task, read all
instructions carefully until you reach START HERE under Task 3**.

2.1 **(12 points)** Complete *4 out of the following 8 exercises* to
dive deeper into your data. All datasets are different and therefore,
not all of these tasks may make sense for your data - which is why you
should only answer *4*.

Make sure that you’re using dplyr and ggplot2 rather than base R for
this task. Outside of this project, you may find that you prefer using
base R functions for certain tasks, and that’s just fine! But part of
this project is for you to practice the tools we learned in class, which
is dplyr and ggplot2.

1.  Plot the distribution of a numeric variable.
2.  Create a new variable based on other variables in your data (only if
    it makes sense)
3.  Investigate how many missing values there are per variable. Can you
    find a way to plot this?
4.  Explore the relationship between 2 variables in a plot.
5.  Filter observations in your data according to your own criteria.
    Think of what you’d like to explore - again, if this was the
    `titanic` dataset, I may want to narrow my search down to passengers
    born in a particular year…
6.  Use a boxplot to look at the frequency of different observations
    within a single variable. You can do this for more than one variable
    if you wish!
7.  Make a new tibble with a subset of your data, with variables and
    observations that you are interested in exploring.
8.  Use a density plot to explore any of your variables (that are
    suitable for this type of plot).

<!-------------------------- Start your work below ---------------------------->

``` r
# Choice 1: Plot the distribution of a numeric variable - I chose to plot the distribution of number of units
choice1 <- apt_buildings %>%
  filter(no_of_units < quantile(no_of_units, 0.95)) %>%
  ggplot (aes(no_of_units, after_stat(density))) +
  geom_histogram(binwidth=20) +
  scale_x_continuous(breaks = seq(0, 300, by=50))
print(choice1)
```

![](Mini-data-analysis-1.md_files/figure-gfm/unnamed-chunk-17-1.png)<!-- -->

``` r
# Choice 2: Create a new variable based on other variables in your data (only if it makes sense) - add a new variable "storey_availability" calculated by # of storeys / # of units
choice2 <- mutate (apt_buildings, storey_availability = no_of_storeys/no_of_units)
print (choice2)
```

    ## # A tibble: 3,455 × 38
    ##       id air_conditioning amenities          balconies barrier_free_accessi…¹ bike_parking exterior_fire_escape fire_alarm garbage_chutes heating_type intercom laundry_room locker_or_storage_room no_of_elevators parking_type pets_allowed
    ##    <dbl> <chr>            <chr>              <chr>     <chr>                  <chr>        <chr>                <chr>      <chr>          <chr>        <chr>    <chr>        <chr>                            <dbl> <chr>        <chr>       
    ##  1 10359 NONE             Outdoor rec facil… YES       YES                    0 indoor pa… NO                   YES        YES            HOT WATER    YES      YES          NO                                   3 Underground… YES         
    ##  2 10360 NONE             Outdoor pool       YES       NO                     0 indoor pa… NO                   YES        YES            HOT WATER    YES      YES          YES                                  3 Underground… YES         
    ##  3 10361 NONE             <NA>               YES       NO                     Not Availab… NO                   YES        NO             HOT WATER    YES      YES          YES                                  0 Underground… YES         
    ##  4 10362 NONE             <NA>               YES       YES                    Not Availab… YES                  YES        NO             HOT WATER    YES      YES          YES                                  1 Ground Leve… YES         
    ##  5 10363 NONE             <NA>               NO        NO                     12 indoor p… NO                   YES        NO             HOT WATER    YES      YES          NO                                   0 Underground… YES         
    ##  6 10364 NONE             <NA>               NO        NO                     Not Availab… <NA>                 YES        NO             HOT WATER    YES      YES          YES                                  0 Ground Leve… YES         
    ##  7 10365 NONE             <NA>               NO        YES                    Not Availab… NO                   YES        NO             HOT WATER    YES      YES          YES                                  0 Surface Par… YES         
    ##  8 10366 CENTRAL AIR      Indoor pool , Ind… YES       NO                     Not Availab… NO                   YES        YES            HOT WATER    YES      YES          YES                                  2 Underground… YES         
    ##  9 10367 NONE             <NA>               YES       YES                    0 indoor pa… NO                   YES        YES            ELECTRIC     YES      YES          NO                                   4 Underground… YES         
    ## 10 10368 NONE             Indoor recreation… YES       YES                    Not Availab… NO                   YES        NO             HOT WATER    YES      YES          NO                                   2 Surface Par… YES         
    ## # ℹ 3,445 more rows
    ## # ℹ abbreviated name: ¹​barrier_free_accessibilty_entr
    ## # ℹ 22 more variables: prop_management_company_name <chr>, property_type <chr>, rsn <dbl>, separate_gas_meters <chr>, separate_hydro_meters <chr>, separate_water_meters <chr>, site_address <chr>, sprinkler_system <chr>,
    ## #   visitor_parking <chr>, ward <chr>, window_type <chr>, year_built <dbl>, year_registered <dbl>, no_of_storeys <dbl>, emergency_power <chr>, `non-smoking_building` <chr>, no_of_units <dbl>, no_of_accessible_parking_spaces <dbl>,
    ## #   facilities_available <chr>, cooling_room <chr>, no_barrier_free_accessible_units <dbl>, storey_availability <dbl>

``` r
# Choice 3: Explore the relationship between 2 variables in a plot - I want to explore the relationship between year built and no_of_units
choice3 <- apt_buildings %>% 
  filter(!is.na(no_of_units) & !is.na(year_built)) %>%
  ggplot(aes(x=year_built, y=no_of_units)) + 
  geom_point() 
print(choice3)
```

![](Mini-data-analysis-1.md_files/figure-gfm/unnamed-chunk-19-1.png)<!-- -->

``` r
# Choice 4: Make a new tibble with a subset of your data, with variables and observations that you are interested in exploring
class(apt_buildings)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

``` r
choice4 <- select(apt_buildings, year_built, no_of_units, no_of_storeys, no_of_elevators, air_conditioning)
print(choice4)
```

    ## # A tibble: 3,455 × 5
    ##    year_built no_of_units no_of_storeys no_of_elevators air_conditioning
    ##         <dbl>       <dbl>         <dbl>           <dbl> <chr>           
    ##  1       1967         218            17               3 NONE            
    ##  2       1970         206            14               3 NONE            
    ##  3       1927          34             4               0 NONE            
    ##  4       1959          42             5               1 NONE            
    ##  5       1943          25             4               0 NONE            
    ##  6       1952          34             4               0 NONE            
    ##  7       1959          14             4               0 NONE            
    ##  8       1971         105             7               2 CENTRAL AIR     
    ##  9       1969         571            32               4 NONE            
    ## 10       1972         171             4               2 NONE            
    ## # ℹ 3,445 more rows

<!----------------------------------------------------------------------------->

2.2 **(4 points)** For each of the 4 exercises that you complete,
provide a *brief explanation* of why you chose that exercise in relation
to your data (in other words, why does it make sense to do that?), and
sufficient comments for a reader to understand your reasoning and code.

<!-------------------------- Start your work below ---------------------------->

For Exercise 1, I chose to plot the distribution of number of units to
get an idea of how many units are there in most of apartments in
Vancouver? Based on that, I first filtered the 95% of no_of_units to
cover a great range of data but filter out those extreme ones. Then I
did the histogram to check for the distribution. For Exercise 2, I chose
to add a new variable “storey_availability” calculated by \# of storeys
/ \# of units to check the scarcity of the storeys in apartments. For
Exercise 3, I chose to explore the relationship between year built and
no_of_units to check if there’s any relationship between these two
variables, such as, which years apartments built with the most no of
units? A scatter plot is a good way to visually see if there’s any
correlation between the two. For Exercise 4, I made a new tibble with a
subset of my data by checking the class of the dataset first, and then
use the select function to subset my data that I am interested in
exploring.

<!----------------------------------------------------------------------------->

# Task 3: Choose research questions

**(4 points)** So far, you have chosen a dataset and gotten familiar
with it through exploring the data. You have also brainstormed one
research question that interested you (Task 1.4). Now it’s time to pick
4 research questions that you would like to explore in Milestone 2!
Write the 4 questions and any additional comments below.

<!--- *****START HERE***** --->

Question 1: For the apartment with highest number of units, which year
did it build? Question 2: Is there a positive relationship between
number of units and number of storeys in most of apartments? Question 3:
How many apartments have “central_air” air conditioning? What’s the
proportion of it over all apartments? Question 4: Is there a positive
relationship between number of units and number of elevators in most of
apartments? <!----------------------------->

# Overall reproducibility/Cleanliness/Coherence Checklist

## Coherence (0.5 points)

The document should read sensibly from top to bottom, with no major
continuity errors. An example of a major continuity error is having a
data set listed for Task 3 that is not part of one of the data sets
listed in Task 1.

## Error-free code (3 points)

For full marks, all code in the document should run without error. 1
point deduction if most code runs without error, and 2 points deduction
if more than 50% of the code throws an error.

## Main README (1 point)

There should be a file named `README.md` at the top level of your
repository. Its contents should automatically appear when you visit the
repository on GitHub.

Minimum contents of the README file:

- In a sentence or two, explains what this repository is, so that
  future-you or someone else stumbling on your repository can be
  oriented to the repository.
- In a sentence or two (or more??), briefly explains how to engage with
  the repository. You can assume the person reading knows the material
  from STAT 545A. Basically, if a visitor to your repository wants to
  explore your project, what should they know?

Once you get in the habit of making README files, and seeing more README
files in other projects, you’ll wonder how you ever got by without them!
They are tremendously helpful.

## Output (1 point)

All output is readable, recent and relevant:

- All Rmd files have been `knit`ted to their output md files.
- All knitted md files are viewable without errors on Github. Examples
  of errors: Missing plots, “Sorry about that, but we can’t show files
  that are this big right now” messages, error messages from broken R
  code
- All of these output files are up-to-date – that is, they haven’t
  fallen behind after the source (Rmd) files have been updated.
- There should be no relic output files. For example, if you were
  knitting an Rmd to html, but then changed the output to be only a
  markdown file, then the html file is a relic and should be deleted.

(0.5 point deduction if any of the above criteria are not met. 1 point
deduction if most or all of the above criteria are not met.)

Our recommendation: right before submission, delete all output files,
and re-knit each milestone’s Rmd file, so that everything is up to date
and relevant. Then, after your final commit and push to Github, CHECK on
Github to make sure that everything looks the way you intended!

## Tagged release (0.5 points)

You’ve tagged a release for Milestone 1.

### Attribution

Thanks to Icíar Fernández Boyano for mostly putting this together, and
Vincenzo Coia for launching.
