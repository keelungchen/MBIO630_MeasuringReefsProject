MBIO630_GroupProject_MeasuringReefs
================
Elizabeth Madin
2022-09-22

## Summary:

This sub-module focuses on measuring and comparing coral patch reefs in
the field and with satellite, aerial (airplane and drone) imagery of
various spatial resolutions, as well as GPS tracking.

We’re using this exercize as a means to understand the general
implications of satellite imagery spatial resolution on measuring
features of interest. However, it has real-world applications in terms
of coral reef area measurement (e.g., [Madin and Madin (2015)
Conservation
Biology](https://drive.google.com/file/d/1C_vg4Uju5aTMWh7-Pf0ZhgrRtXSfSMNK/view)
and <https://allencoralatlas.org>)).

## Goals

-   Make connection between use of field data and remote (e.g.,
    satellite; aerial) imagery to measure biological/habitat variables
-   Highlight strengths and limitations of each approach
-   Start thinking about ?s to ask/answer in your own research
-   Gain coral reef field experience
-   Practice using version control (git / Github)
-   Gain experience using R markdown for scientific writing
-   Gain experience with basic data analyses
-   Contribute drone imagery to long-term reef monitoring dataset

## Components

-   Devise/practice field measurement protocol (transect- and
    drone-based)
-   Measure reefs in-situ
-   Measure reefs w/satellite imagery of various spatial resolutions
    via:
    -   Google Earth
    -   Planet Explorer
-   Compare patterns and measurement variability based on method,
    imagery spatial resolution, etc.
-   Write up results as ‘mini-paper’

## Materials

-   transect tapes, weighted: 2 x 50m per group
-   slates w/pencils and loaded w/(blank) underwater sheet for metadata:
    2
-   mesh bag(s) to carry everything
-   GPS
-   waterproof bag (with cord) for GPS
-   drone
-   drone batteries + charger

## Protocols

We will focus on two patch reefs: 20 (small) and 22 (medium)

#### Part 1: Field measurements

Preparation:

-   Brainstorm, plan, and practice measurements on land:
    -   Perimeter only
-   Establish protocol for field measurements
-   Create datasheets on waterproof paper
-   Gather remaining supplies for morning field trip

Measuring reefs:

-   Measure each study reef based on methods in protocol
-   Record data (including metadata - e.g., date/time, depth, etc.) on
    datasheet(s)
-   Make sure not to leave any gear in the water!

Data entry:

-   Go to [the Github repository for this
    sub-module](https://github.com/MBIO630-Remote-Sensing-2022/MBIO630_GroupProject_MeasuringReefs)
    and click the green “Code” button -\> “Download ZIP” -\> save on
    your machine
-   Open the .csv datasheet template (data/MeasuringReefs_template.csv)
    -   IMPORTANT: Do not add/delete columns since we will combine
        datasets later
    -   rename “MeasuringReefs.template.csv” to
        “MeasuringReefs_YourInitials.csv” (e.g.,
        “MeasuringReefs_EPM.csv”)
    -   rename “MBIO630_GroupProject_MeasuringReefs.Rmd” to
        “MBIO630_GroupProject_MeasuringReefs_YourInitials.Rmd”
-   Choose one person from each group to enter the group’s transect data
    -   All others should delete the four rows (2-3 & 28-29) where
        column “method” = “field”
    -   The group’s data compiler (only) will enter transect & GPS data
        into this datasheet
    -   The column headings you’ll be filling in are:
        -   perimeter_m
        -   area_m2 (use the formula =((C2/(2*PI()))^2)*PI() to
            calculate this from perimeter)
        -   date
        -   observer (as your two or three initials)
        -   notes (if needed)

#### Part 2: Imagery measurements

Getting started:

-   Open .kmz/.kml patch reef placemark file (“FieldSites.kmz”) by
    dragging into Google Earth
-   Open .csv datasheet you saved with your initials
    -   Column headings you’ll be filling in are:
        -   perimeter_m
        -   area_m2
        -   observer (as your two or three initials)
        -   notes (if needed)

Measuring reefs:

-   You will measure two of the patch reefs in Kane’ohe Bay for:
    -   Perimeter
        -   use the formula =((C2/(2*PI()))^2)*PI() to calculate area
            from perimeter) in .csv (you’ll need to change cell C2 to
            whatever row it’s in)
-   Do three replicates of each reef
-   You will use both Google Earth and Planet Explorer to measure reefs
    using imagery spanning a range of spatial resolutions

1)  **Google Earth**

    -   Create a folder in My Places (Add -\> Folder); give it a name
        that makes sense (eg, “KBay patch reefs”)

        -   Keep this folder highlighted from now on while you’re
            measuring reefs so the measurements will go straight into
            that folder

    -   Measure each of the study reefs for the following dates/spatial
        resolutions by using the Time Slider to select the following
        dates’ imagery:

        | Date (yyyymmdd) | Resolution (m) | Satellite                             | Provider |
        |:----------------|:---------------|:--------------------------------------|:---------|
        | 20130115        | 0.15           | NA; aerial imagery                    | Unknown  |
        | 20130822        | 0.50           | WorldView-1/2, GeoEye-1, or Quickbird | Maxar    |
        | 20110108        | \~1.00         | Ikonos                                | Maxar    |
        | 20030412        | \~2.00         | EarlyBird-1 (?)                       | Maxar    |

    -   Use the polygon measurement tool to extract perimeter

    -   Manually copy measurements into .csv

    -   Save measurement: name as “PR##*\#.##*\##*\##” = PR\[reef \#\] *
        \[resolution, in m\] \_ \[your initials\] \_ \[replicate
        number\] (e.g., “PR20_0.15_EM_01”)

    -   If any of your measurments show up in Temporary Places, drag
        saved measurements to the folder you created in My Places

    -   Frequently save My Places! (File -\> Save -\> Save My Places)

        -   *Note*: if you need to go back to measurements, right-click
            on outlines (or their corresponding saved names in My
            Places) -\> Get Info

2)  **Planet Explorer**

    -   Use the upper left hand search bar to navigate to Kane’ohe Bay

    -   Visually compare the Google Earth placemarks with the Planet
        Explorer AOI to locate your study reefs

    -   Clear the AOI that’s automatically drawn (click rubbish bin icon
        adjacent to left-hand draw AOI tool)

    -   Draw a rectangular AOI (area of interest) to cover the two study
        reefs (a regular AOI, not a “constrained” AIO)

        -   *Note*: don’t use ‘shift’ to draw a freehand AOI (you may
            not see imagery availablity if drawn by freehand, for some
            strange reason)

    -   Use the lower left hand gear icon (settings) to change the units
        from km to m

    -   Under heading “Filter”, set the following search parameters:

        -   Un-tick box under “Spectral bands must include…near infrared
            (NIR)”
        -   Cloud cover = 0-10%
        -   Area coverage = 90-100%
        -   Source = tick sources corresponding to “satellite” below
        -   *Tip*: do this satellite by satellite for faster searching
        -   Turn toggle on for “Show full catalog”

    -   Under heading “Dates”, set range to \~ 1 week before and after
        each of the dates below, one by one

    -   Measure each of the study reefs for the following
        satellites/dates/spatial resolutions by using the left-hand
        options area to scroll to and select the following imagery:

        | Date (yyyymmdd) | Resolution (m) | Satellite                            | Provider |
        |:----------------|:---------------|:-------------------------------------|:---------|
        | 20190316        | \~3.00         | PlanetScope (formerly Dove CubeSats) | Planet   |
        | 20160208        | 5.00           | RapidEye (ortho tile)                | Planet   |
        | 20180307        | \~10.00        | Sentinel-2                           | ESA      |
        | 20190328        | 30.00          | Landsat 8                            | USGS     |

    -   Zoom in to the point where you feel you can most accurately
        outline the reefs

    -   Use the “measure distance” tool to extract perimeter (by
        clicking to make many vertices)

    -   Manually copy measurements into .csv

        -   *Note*: you can save measurements (search icon -\> “save
            search” button), but it’s a bit clunky so we won’t;
            double-check each entry for accuracy before moving on

## Part 3: Data merging and analysis

Once all data is collected, merge datasets:

-   Check your dataset for any typos, missing values, etc.
-   Check that your dataset is saved in the “data” folder
-   Drop your own dataset into the class Slack channel (general)
-   The group data compiler will merge everyone’s dataset in a new
    master .csv file (i.e.,, “MeasuringReefs_Master.csv”), using their
    own dataset (which contains the field data) as the base file
-   Once finished, the group data compiler should drop the master file
    back into the Slack channel
-   Download the master data file and save to your on machine (in the
    “data” folder)

Then analyze data:

-   In RStudio, open the .Rmd file
-   Make some basic plots to help you explore any patterns in the data
-   Run some statistical analyses to determine sources of variance, any
    significant trends, etc.

Here are a few basic plots to get you started - you can copy this code
or write your own:

\_Note: you’ll need to change the data source file name to
“…*Master.csv”, and your results will be different than mine as a
result.*

``` r
################################################
# explore patterns
################################################

# Effect of method
boxplot(area_m2~method, data=data, na.ignore=TRUE, col="lightgrey",
     ylab="Patch reef area (m^2)", 
     xlab="Method", 
     main="Area versus method")
```

<img src="MBIO630_GroupProject_MeasuringReefs_files/figure-gfm/data explore-1-1.png" style="display: block; margin: auto;" />

``` r
dev.copy(pdf,"output/method_area_effect.pdf")    # can change to .png, etc.; can change size to incr resolution
dev.off()

# Effect of imagery resolution
## on area
plot(area_m2~imagery_resolution_m, data=data, col="slategrey",
     xlim=c(0,10),
     xlab="Imagery spatial resolution (m)", 
     ylab="Patch reef area (m^2)", 
     main="Area versus imagery resolution")
res.area.lm=lm(area_m2 ~ imagery_resolution_m, data=data)
abline(res.area.lm, col = "black")
```

<img src="MBIO630_GroupProject_MeasuringReefs_files/figure-gfm/data explore-1-2.png" style="display: block; margin: auto;" />

``` r
summary(res.area.lm)
dev.copy(pdf,"output/resolution_area_effect.pdf")    
dev.off()

## on perimeter
plot(perimeter_m~imagery_resolution_m, data=data, col="slategrey",
     xlim=c(0,10),
     xlab="Imagery spatial resolution (m)", 
     ylab="Patch reef perimeter (m)", 
     main="Perimeter versus imagery resolution")
res.perim.lm=lm(perimeter_m ~ imagery_resolution_m, data=data)
abline(res.perim.lm, col = "black")
```

<img src="MBIO630_GroupProject_MeasuringReefs_files/figure-gfm/data explore-1-3.png" style="display: block; margin: auto;" />

``` r
summary(res.perim.lm)
dev.copy(pdf,"output/resolution_perimeter_effect.pdf")    
dev.off()

# Effect of date (i.e., do patch reefs measurably grow or shrink over time?)
plot(area_m2~as.numeric(year), data=data, col="slategrey",
     xlab="Year", 
     ylab="Patch reef area (m^2)", 
     main="Area versus year")
date.area.lm=lm(area_m2 ~ as.numeric(year), data=data)
abline(date.area.lm, col = "black")
```

<img src="MBIO630_GroupProject_MeasuringReefs_files/figure-gfm/data explore-1-4.png" style="display: block; margin: auto;" />

``` r
summary(date.area.lm)
dev.copy(pdf,"output/date_area_effect.pdf")    
dev.off()
```

Now, let’s see if there’s anything going on with time when imagery
resolution is considered:

``` r
################################################
# analyze data
################################################

# Effects of imagery resolution + year

## Note: interpretation below is for my test data; your data's results may be different
data$year <- as.numeric(data$year) 
res.year.lm=lm(area_m2 ~ imagery_resolution_m * year, data=data) # run interaction model
summary(res.year.lm)      # overall model is significant, but not indiv parameters (ie, predictor variables)
anova(res.year.lm)        # run ANOVA to look at predictor variables in isolation
drop1(res.year.lm, test="F")  # use drop1 function to see which parameter can be dropped (test="F" adds type 
                          # II ANOVA)
res.year.lm2 <- lm(area_m2 ~ imagery_resolution_m + year, data=data)
                          # re-run model w/o interaction term that drop1 said to drop
summary(res.year.lm2)     # model now says both predictor variables are significant
drop1(res.year.lm2, test="F") # drop1 says neither remaining variable can be dropped
```

Or reef identity (reef number):

``` r
################################################
# analyze data
################################################

# Effects of imagery resolution + reef ID
res.reefID.lm=lm(area_m2 ~ imagery_resolution_m * reef_no, data=data)
summary(res.reefID.lm)  
              # I get NAs for variable reef_no since only one reef used in my dataset
```

## Part IV: Discussion questions

-   Discuss as a group any patterns that seemed to emerge…e.g.,
    -   Which method did you find to be more variable among
        groups/individuals - field or imagery?
    -   How did imagery resolution affect your measurements?
    -   What are the trade-offs between field vs imagery measurements?
    -   What are the trade-offs between the different imagery a)
        platforms and b) resolutions?

## Part V: Write-up

-   When you’re finished with your analyses, go back and give each
    figure a short caption
-   Structure your .Rmd file as a ‘mini-paper’ with a bit of very brief
    text (\~2-5 sentences) for each of the usual paper sections:
    -   Introduction (summarize what you’re doing with this
        mini-project)
    -   Methods (what you did, both in the field and the lab)
    -   Results (here’s where your figures and stats outputs will go)
    -   Discussion (mention any interesting findings and, if you have
        time, briefly relate this to any previous literature using a
        similar approach/asking similar questions)
-   Upload your project folder to Github and send the link to Liz via
    Slack when complete (this is how you’ll turn it in)
    -   A helpful step-by-step guide to version control with git/Github
        is [here](https://jmadinlab.github.io/data_code_tutorial/).
    -   If you have trouble with git/Github after following the steps in
        this guide, reach out to one of the instructors.
-   Some tips:
    -   If you’re new to RMarkdown, use the cheat sheets in the info
        folder to help with your write-up
    -   If you’re new to writing manuscripts, [this is a handy
        guide](https://conservationbytes.com/2012/10/22/how-to-write-a-scientific-paper/)
        that lays out the process in clear steps (not all steps will
        apply to this write-up, but most will for your independent
        project write-up)
-   This exercise will help you see the value of using R Markdown to
    write papers!!!
