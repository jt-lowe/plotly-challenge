# plotly-challenge
## Monash Data Course WK15


For this assignment, we built an interactive dashboard based on data that was provided that gives information about microbes that are found in the Belly Button of the study participants.

### Creating the dropdown menu

First we read the samples.json file using the d3.json function, then we select the '#selDataset' id and run through each 'names' value that is in the data, appending it into the id with the <option> property, this creates a selector for each 'id' that is in the dataset and makes it so we can select a participant, pulling up the data that is relevant to them.

### Demographic Info

The first step is to read in our data using the d3.json methond, focussing only on the metadata from our samples.json file. We also create a filter function to assess for only the selected value from the dropdown selection on our page.

We use d3 to select the '#sample-metadata' id location for where our data will be displayed, then we append a <p> and append the text of the key value pairs into the id forEach pair that is in the object.

### Plotting the charts

The first step was to create a horizontal bar chart for the top 10 OTUs found for a specified individual.

This was completed in the createCharts function within the app.js file. The first step is to call in the data using the d3.json function on our samples.json file. We then utilise the then() function to perform the chart building on the values we are interested in, this keeps the data open and available for use in the file.

Each endpoint in the data is read in and stored as an object variable under it's name, we also ensure the data that is being displayed is the data that has been selected from the dropdown by using a filter function.

For the bar chart, the 'sample_values' were used for the x axis, we formatted the 'otu_ids' to be the y axis labels (as the id straight from the file is a number we had to create a string to append "OTU " to the number as to provide our label) and we created hover text from the 'otu_labels'.

Particular for this function, the 'orientation' definition was used to ensure that the bar chart was horizontal (i.e. 'h'), and we use the slice(0,10) function to ensure we are getting the top 10 values.

Next we create a bubble chart, using 'otu_ids' for both the x-values and marker colors, 'sample_values' for the y-values and marker size and 'otu_labels' for the text values.

In this function, we also read in our metadata info as to create our gauge chart, which collects the wfreq value, and plots it on a gauge where the range is 0-9.

All 3 plots are plotted into their corresponding element in the index.html file. (i.e. 'bar' for the bar etc)

