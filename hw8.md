---
layout: page
title: Homework 8 - UFO Sightings
permalink: /hw8/
---

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<a href="https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/ufo-scrubbed-geocoded-time-standardized-00.csv">The Data</a> |
<a href="https://github.com/aanyakr/aanyakr.github.io/blob/main/Workbook.ipynb">The Analysis</a>

## UFO Sightings per Year by Shape

<div id="vis1" style="width:100%"></div>
<script>vegaEmbed('#vis1', '{{ site.baseurl }}/ufo_chart1.json');</script>

This line chart shows how many UFO sightings were reported each year from 1990 to 2013 for the six most commonly reported shapes: light, triangle, circle, fireball, sphere, and disk. Year is encoded on the x-axis as an ordinal (O) variable, the number of sightings on the y-axis as a quantitative (Q) variable, and shape as color, which is a nominal (N) variable. I used Altair’s default categorical color scheme because shape has no natural order, so each shape just needs its own distinct color rather than a gradient. In my Python notebook, I named the columns since the file has no header row, converted the date column to datetime format, and pulled out the year. I then filtered to the six most common shapes and to 1990–2013, since there are very few reports before 1990 and the data ends partway through 2014, which would have made it look like sightings suddenly dropped. Finally, I grouped the data by year and shape and counted the number of sightings in each group.
For the first plot, I added a legend selection, so clicking a shape in the legend highlights that shape’s line and fades the others. With six overlapping lines the chart can be hard to read, and this makes it easy to follow one shape at a time and compare trends. For example, highlighting individual shapes shows that “light” was the most reported shape for nearly every year, while “disk” sightings stayed fairly flat after 2000. “Fireball” reports, by contrast, jumped sharply around 2012, almost tripling from 2010.

## Top 15 States for UFO Sightings

<div id="vis2" style="width:100%"></div>
<script>vegaEmbed('#vis2', '{{ site.baseurl }}/ufo_chart2.json');</script>

This bar chart shows the 15 US states with the most reported UFO sightings. The number of sightings is encoded on the x-axis as a quantitative (Q) variable and state on the y-axis as a nominal (N) variable, with the bars sorted from most to least so the ranking is easy to read. I also colored the bars by sighting count using the sequential “purples” color scheme, so states with more sightings appear darker. A sequential scheme fits here because count goes from low to high, and the darker bars draw the eye to the top states. For this plot, I filtered the data to only sightings in the US, counted the sightings in each state, and kept the top 15. California stands out with about 8,900 sightings, more than double Washington and Florida, which come next with just under 4,000 each.
