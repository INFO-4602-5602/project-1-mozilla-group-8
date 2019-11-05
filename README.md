Team 8 Categorical Visualization (Bubble Chart)
Names: Joshua Baker, Angus MacDonald, Malik Tefridj, Keaton Whitehead


<h2>Team Roles per Individual:</h2>
	Josh Baker: Mapped quantitative data 
	Angus MacDonald: Set up categorical bubble chart
	Malik Tefridj: Set up quantitative data for visualization in Python
	Keaton Whitehead: Set up categorical data html/CSS overall layout


<h2>Sources:</h2> 
	1.) Bubble Chart Template/Format: https://bl.ocks.org/alokkshukla/3d6be4be0ef9f6977ec6718b2916d168
	2.) Tooltip: https://www.d3-graph-gallery.com/graph/bubble_tooltip.html
	3.) Loading Data from Excel sheet to JSON/Javascript: https://github.com/SheetJS/sheetjs
	4.) ....??? any others....


<h2>Instructions for Project Execution:</h2>
<h3>Categorical</h3>
<ol>
	<li>Download project files onto localhost machine and insert the files into a single directory.
	<li>In a terminal/command prompt window, navigate to the project directory (cd ...).
	<li>Once inside the project directory, host python server for the webpage to run on (example: "python -m http.server")
	<li>In web browser, go to localhost (127.0.0.1), specifying whichever port is used (example: "127.0.0.1:8000" for port 8000)
	<li>Open "categorical.html" and allow to load (time delay due to data loading and processing)
	<li>To interact, hover mouse over any bubble to get a summary of information contained within that bubble about the dataset.
</ol>

<h3>Quantitative</h3>
<ol>
	<li>Open "devicesbycountry.html" in the browser - no need to start a server.
	<li>To interact, hover mouse over any country to see the average number of devices owned.
</ol>


<h2>Visualization Information:</h2>
<h3>Categorical</h3>
The categorical analysis creates a bubble chart for each rank of importance to compare the ratings that users provided to show what they prioritize the most in selecting a technological product such as privacy, price, features, user reviews, etc. The bubble charts have the ability to show what users rated in each priority and which seemed to have equivalent priorities. For example, viewers can see the breakdown for the most important priority (rated #1) by comparing the relative sizes of the bubbles to each other. Each bubble represents one aspect that the user rated on, and each bubble is labeled on the screen. Additionally, the viewer can hover over each bubble with their mouse to get a summary of the information portrayed by that bubble. Each seperate box represents the different orders of priorities for each topic and the population of those rankings.


<h3>Quantitative</h3>
The quantitative analysis uses a map to compare the average number of internet-connected devices people own by country. We used Python to process the data so that it was narrowed down to the average number of devices that people owned. We then grouped the averages by country and saved it as its own CSV file. Next, we used Tableau to map the data out. The average devices owned affects the color of the country, which can be seen on the legend. You can hover over individual countries to see the exact averages, as well as the total number of people that responded to the Mozilla survey from said country. Using Tableau Public we were able to directly embed the interactive visualization in a basic HTML file.


<h2>Design Process:</h2
<h3>Categorical</h3>
To automate the data processing and loading, we editted the data file to a smaller size by keeping only the necessary data for this visualization (data is still mutable), then created a second Excel sheet that autopopulates and updates with the sums for each rating per category. Therefore, if the information is ever changed in the Excel sheet, the numbers will automatically update. The calculations from the second Excel sheet are uploaded into JSON format using 'xlsx.full.min,' a file downloaded from a library designed to convert Excel data into a JSON format for webpages. An array of objects is then created using the JSON formatted variable, where each object holds the information for one bubble set. From there, using D3, a bubble chart visualization is created, where teh radius of each bubble depends on the value of "Count", or the number of specified ratings that the respective attribute received.


<h3>Quantitative</h3>
In order to make the data easier to aggregate and visualize, we decided to use python pandas library in order to get true counts. Loading in the csv, we were able to use the 'groupby' function on the country column as long with the 'aggregate' count function. With this organization, we were able to get a country breakdown of device usage.
We wanted there to be a distinct difference between countries above and below the average for the visualization. However, a few very small countries that only had a couple responses raised the maximum average so much that a lot of countries were indistinguishable. To remedy this, we lowered the maximum of the color scale, and set the center of the color scale to the overall average number of devices owned. Since Mozilla's landmark software is Firefox, we made the color scale similar to the main colors of the Firefox logo (orange and blue). Countries below the average are gradually tinted bluer, while countries above the average are tinted orange. 


