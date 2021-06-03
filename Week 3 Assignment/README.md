<h1>Segmenting and Clustering the Neighborhood in Toronto</h1>

<h2>Table of contents</h2>

<div class="alert alert-info alert-info" style="margin-top: 20px">

1. [Scraping Wikipedia page and Transforming the data on Wiki page into pandas dataframe](#1)<br>
2. [Attaching Geopatial Coordinates of Toronto City to respective Postal Codes and creating a Dataframe](#2)<br>
3. [Analyze Each Neighborhood](#3)<br>
4. [Conclusion](#4)<br>
</div>
<hr>

<h2>Scraping Wikipedia page and Transforming the data on Wiki page into pandas dataframe</h2><a id="1"></a> 
<p>In this section, I scraped data from <A href='https://en.wikipedia.org/w/index.php?title=List_of_postal_codes_of_Canada:_M&oldid=945633050'><u>wikipedia</u></A> page and cleand it to convert in the form below:</p>

| | PostalCode |          Borough |                                      Neighborhood |
|-| ---------- | ---------------- | ------------------------------------------------- |
|0|        M5G | Downtown Toronto |                                Central Bay Street |
|1|        M2H |       North York |                                 Hillcrest Village |
|2|        M4B |        East York |                   Woodbine Gardens, Parkview Hill |
|3|        M1J |      Scarborough |                               Scarborough Village |
|4|        M4G |        East York |                                           Leaside |
|5|        M4M |     East Toronto |                                   Studio District |
|6|        M1R |      Scarborough |                                 Maryvale, Wexford |
|7|        M9V |        Etobicoke |  Albion Gardens, Beaumond Heights, Humbergate,... |
|8|        M9L |       North York |                                     Humber Summit |
|9|        M5V | Downtown Toronto | CN Tower, Bathurst Quay, Island airport, Harbo... |

<p>To scrap the data on <A href='https://en.wikipedia.org/w/index.php?title=List_of_postal_codes_of_Canada:_M&oldid=945633050'><u>wikipedia</u></A> page, I used Beautifulsoup library. Then I cleaned and organised the obtain data using following steps:
<Blockquote>
    <ul>
        <li>Removed rows with 'Not assigned' values in "Borough" column</li>
        <li>Grouped neighborhoods with same "PostalCode" and "Borough"</li>
        <li>Assigned Borough's value to 'Not assigned' value of "Neighborhood"</li>
    </ul>
    </Blockquote>
Finally, I stored the obtained dataframe in CSV file as 'toronto_cleaned.csv'</p>

<h2>Attaching Geopatial Coordinates of Toronto City to respective Postal Codes and creating a Dataframe</h2><a id="2"></a>
<p>In this section, I merged both the CSV files namely 'toronto_cleaned.csv' and 'Geopatial_Coordinates.csv' then I stored the obtained Dataframe in a CSV file as 'toronto_updated.csv' . The obtained dataframe looks as below:</p>

| | PostalCode |          Borough |                                      Neighborhood |  Latitude |  Longitude |
|-| ---------- | ---------------- | ------------------------------------------------- | --------- | ---------- |
|0|        M5G | Downtown Toronto |                                Central Bay Street | 43.657952 | -79.387383 |
|1|	       M2H |       North York |                                 Hillcrest Village | 43.803762 | -79.363452 |
|2|        M4B |        East York |                   Woodbine Gardens, Parkview Hill | 43.706397 | -79.309937 |
|3|	       M1J |      Scarborough |                               Scarborough Village | 43.744734 | -79.239476 |
|4|	       M4G |        East York |                                           Leaside | 43.709060 | -79.363452 |
|5|        M4M |     East Toronto |                                   Studio District | 43.659526 | -79.340923 |
|6|	       M1R |      Scarborough |                                 Maryvale, Wexford | 43.750072 | -79.295849 |
|7|	       M9V |        Etobicoke | Albion Gardens, Beaumond Heights, Humbergate, ... | 43.739416 | -79.588437 |
|8|	       M9L |       North York |                                     Humber Summit | 43.756303 | -79.565963 |
|9|	       M5V | Downtown Toronto | CN Tower, Bathurst Quay, Island airport, Harbo... |	43.628947 |	-79.394420 |
|10|	   M1B |      Scarborough |                                    Rouge, Malvern | 43.806686 | -79.194353 |
|11|	   M5A | Downtown Toronto |	                                     Harbourfront | 43.654260 | -79.360636 |

<h2>Analysing Each Neighborhood</h2><a id="3"></a>
<p>In this section, firstly I used Geopy Library to obtain the latitude and longitude values of Toronto City. Then I created a map of Toronto with neighborhood superimposed on top. Next, I used following steps :</p>
<blockquote>
    <ul>
        <li>Filterd boroughs that contain the word Toronto</li>
        <li>Used Foursquare API to explore the neighborhoods</li>
        <li>Find out how many unique categories can be created from all the returned venues</li>
        <li>Created the new dataframe and display the top 10 venues for each PostalCode</li>
        <li>Clusterd Areas using K means algorithm</li>
        <li>Visualized the resulting clusters</li>
        <li>Examine all the five cluster</li>
    </ul>
</blockquote>

<h2>Conclusion</h2><a id="4"></a>
<p>Most of the neighborhoods fall into Cluster 1 which are mostly business areas with cafe, restaurants, supermarkets etc. Cluster 2 are (Restaurants, Pool and Garden) , Cluster 3 are (Park, Trail and Donut Shop) Cluster 4 (Restaurants, Pub, Studio and Store), and lastly Cluster 5 are (Bus line, Swim School and Escape Room).</p>