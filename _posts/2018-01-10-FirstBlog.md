---
layout: post
title: MTA project

---

### 0. Project Motivation

This project was designed to improve data acquisition, data manipulation, data visualization, and data analysis skills with Python.



### 1. Project Description

Our client, WomenTechWomenYes (WTWY) has an annual gala at the beginning of the summer each year. As WTWY is a new and vibrant organization, they want to fill the event with people passionate about increasing the participation of women in technology. They want us to optimize the placement of the street team so that they can gather the most signatures, especially who are willing to attend and donate to the organization.



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

First, I acquired MTA turnstile data from <a href="http://web.mta.info/developers/turnstile.html"> MTA turnstile info </a>
I grouped the data by the station, day, and time period and added turnstile traffic to derive the total traffic. The previous dataframe and the merged data format are as follow. 
[Before: Turnstile Traffic](/path/to/daily traffic.png){:class="img-responsive"}
#[After: Total Traffic](/path/to/image.jpgimage.jpg){:class="img-responsive"}





<img daily traffic>
