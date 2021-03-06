---
layout: post
title: (Data Cleaning) How should we allocate our advertisement team into NYC subway stations?

---

### 0. Project Motivation

This project was designed to improve data acquisition, data manipulation, data visualization, and data analysis skills with Python.
<br>

### 1. Project Description

Our client, WomenTechWomenYes (WTWY) has an annual gala at the beginning of the summer each year. As WTWY is a new and vibrant organization, they want to fill the event with people passionate about increasing the participation of women in technology. They want us to optimize the placement of the street team so that they can gather the most signatures, especially who are willing to attend and donate to the organization.
<br>

### 2. Data

<style type="text/css">
  table {
    margin-left: 0;
    margin-bottom: 24px;
    border-spacing: 0;
    border-bottom: 2px solid black;
    border-top: 2px solid black;
}
table th {
    padding: 3px 10px;
    background-color: white;
    border-top: none;
    border-left: 1px solid black;
    border-right: 1px solid black;
    border-bottom: 1px solid black;
}
table td {
    padding: 3px 10px;
    border-top: none;
    border-left: 1px solid black;
    border-bottom: none;
    border-right: 1px solid black;
}
</style>


<table>
<colgroup>
<col width="30%" />
<col width="70%" />
</colgroup>
<thead>
<tr class="header">
  <th><b>Data Source</b></th>
  <th><b>Reason</b></th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">MTA Turnstile Traffic</td>
<td markdown="span">Determine busiest stations</td>
</tr>
  
<tr>
<td markdown="span">Station GPS Location</td>
<td markdown="span">Find a zipcode for each station</td>
</tr>
 
<tr>
<td markdown="span">NYC Tax Declaration</td>
<td markdown="span">Find financially empowered districts</td>
</tr>

<tr>
<td markdown="span">Google/Bingle Maps</td>
<td markdown="span">Complement missing GPS data</td>
</tr>

</tbody>
</table>

### 3. Analysis


<b>3-0. Data Cleaning</b>

I acquired MTA turnstile data from <a href="http://web.mta.info/developers/turnstile.html"> MTA turnstile info </a>
. I then grouped the data by the station, day, and time period and added turnstile traffic to derive the total traffic. The previous dataframe and the merged dataframe are as follow. 


[Before: Turnstile Traffic]

<img src="/images/daily traffic.png" width="700">


[After: Total Traffic]

<img src="/images/total traffic.png" width="350">

<br>
<b>3-1. Analysis</b>

The following graph shows the busiest station for different time periods throughout the week.
![_config.yml](/images/most traffic.png)

As expected, weekday traffic is higher than weekend traffic and the number of subway passengers goes up rapidly around the morning rush hour. Penn Station on the 34th street turned out to be the busiest station in New York City for most time periods. In order to see more detail of the specific time period, I plotted top 12 busiest stations from 4 PM to 8 PM on Thursday.

<br>
<img src="/images/most traffic_thurs.png" width="700">
<br>

The Penn station turned out to be the busiest station during this time and it is followed by the 23rd and Times Square stations. However, the penn station is one of the largest stations in New York City and it is not a good idea to promote the event in all entrances. In order to consider the size of each station, I divided the traffic by the number of entrances as follow.

<br>
<img src="/images/Benson/Traffic By Entrance.png" width="700">
<br>

Now, the penn station is not the busiest anymore and the 86th street station at the upper east side has the most traffic per station. This is because the penn station has 16 entrances while the 86th station has only one entrance.

Next, I will merge the previous data with the income distribution data by matching GPS coordinates and zip codes. Prior to combining the two data, I calculated the weighted mean income by zip codes in order to identify the areas with more potential donators.

<br>
<img src="/images/Benson/income.png" width="700">
<br>

The weighted mean income varies a lot from region to region. Soho and Tribeca areas tend to be wealthier than other regions. In order to combine the income data with the traffic data, I picked the top 10 stations in terms of wealth and then sorted the stations by the size of traffic.

<br>
<b>4. Conclusion</b>

I used two main data sources to recommend the best stations for the Summer Gala promotion: 1)New York City MTA subway turnstile data and 2)New York State income distribution by zip codes. According to the brief analysis, the penn station has the most traffic for most time periods. However, the 86th street turned out to be the most crowded when the number of entrances is considered. In order to maximize the probability of gathering donations, I filtered the stations based on the mean income of the neighborhood and then selected the 5 busiest stations out of the candidates. According to the analysis, my top 5 recommendations are Chambers Street, Wall Street, Lexington Avenue, 51st Street, and Bowling Green.
