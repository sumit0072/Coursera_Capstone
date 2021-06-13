<h1>The Battle of Neighborhood</h1>
<h2>Introduction</h2>
<p>For many shoppers, visiting shopping malls is a great way to relax and enjoy themselves during weekends and holidays. They can shop grocery and various fashion outlets, dine at restaurants, watch movies and perform many more activities. Shopping malls are like one-stop destination for all types of shoppers. For retailers, the central location and the large crowed at the shopping malls provides a great distribution channel to market their products and services. Property developers are also taking advantage of this trend to build more shopping malls to cater to the demand. As a result, there are many shopping malls in the city of Kuala Lumpur and many more are being built. Opening shopping malls allows property developers to earn consistent rental income. Of course, as with any business decision, opening a new shopping mall requires serious consideration and is a lot more complicated than it seems. Particularly, the location of the shopping mall is one of the most important decisions that will determine whether the mall be a success or a failure.</p>

<h2>Business Problem</h2>
<p>The objective of this capstone project is to analyze and select the best locations in the city of Kuala Lumpur, Malaysia to open new shopping mall. Using data science methodology and machine learning techniques like clustering, this project aims to provide solutions to answer the business question : In the city of Kuala Lumpur, Malaysia, if a property developer is looking to open a new shopping mall, where would you recommend that they open it ?</p>
<h3>Target Audience of this project</h3>
<p>This project is particularly useful to property developers and investors to open or invest in new shopping malls in the capital city of Malaysia i.e. Kuala Lumpur. This project is timely as the city is currently suffering from oversupply of shopping malls. Data from the National Property Information Center (NPIC) released last year showed that an additional 15 per cent will be added to existing mall space and the agency predicted that total occupancy may dip below 86 per cent. The local newspaper The Malay Mail also reported in March last year that the true occupancy rates in malls may be as low as 40 per cent in some areas, quoting a Financial Times (FT) article cataloging the country's continued obsession with building more shopping space despite chronic oversupply.</p>
<h2>Data Description</h2>
<h4>To solve the problem, we will need the following data : </h4>
<blockquote>
    <ul>
        <li>List of neighborhoods in Kuala Lumpur. This defines the scope of this project which is confined to the city of Kuala Lumpur, the capital city of the country of Malaysia in the South East Asia.</li>
        <li>Latitude and Longitude coordinates of those neighborhoods. This is required in order to plot the map and also to get the venue data.</li>
        <li>Venue data, particularly data related to shopping malls. We will use this data to perform clustering on the neighborhoods.</li>
    </ul>
</blockquote>

<h4>Sources of data and methods to extract them</h4>
<p>The <a href='https://en.wikipedia.org/wiki/Category:Suburbs_in_Kuala_Lumpur'>Wikipedia page</a> contains a list of neighborhoods in Kuala Lumpur, with a total of 71 neighborhoods. We will use web scrapping techniques to extract the data from Wikipedia page, with the help of Python 'requests' and 'beautifulsoup' libraries. Then we will get the geographical coordinates of the neighborhoods using Python 'Geocoder' library which will give us the latitude and longitude coordinates of the neighborhoods.</p>

<p>The output shows the final dataset. The dataset consists of a single dataframe with 3 columns containing 'Neighbohood', 'Latitude' and 'Longitude'. 'Neighborhood' column contains the Federal Territory of Kuala lumpur.</p>