# Belly-Button-Biodiversity

## Overview of Project
Roza has a partially completed dashboard that she needs to finish. She has a completed panel for demographic information and now needs to visualize the bacterial data for each volunteer. Specifically, her volunteers should be able to identify the top 10 bacterial species in their belly buttons. That way, if Improbable Beef identifies a species as a candidate to manufacture synthetic beef, Roza's volunteers will be able to identify whether that species is found in their navel.

1. Deliverable 1: Create a Horizontal Bar Chart
2. Deliverable 2: Create a Bubble Chart
3. Deliverable 3: Create a Gauge Chart
4. Deliverable 4: Customize the Dashboard
5. Deliverable 5: A written report on the Belly Button Biodiversity Dashboard analysis

## Resources and Before Start Notes:

* Data Source: BellyButton_bar_chart_starter_code.js, BellyButton_bubble_chart_starter_code.js, BellyButton_bubble_chart_starter_code.js and index.html
* Data Tools: ECMAScript, JavaScript, JSON and IO (Web Server)
* Software: ES6+, ECMAScript and Visual Studio Code 1.50.0

# Functional JavaScript
The map() Method
The map() method in JavaScript applies a transformation to each element in an array. Like a for loop, it can perform an operation to every element of an array.

Here is an example in which all the numbers of an array are doubled:

![Screenshot_20221122_014853](https://user-images.githubusercontent.com/107443962/203428073-c7465adb-fde2-4023-a8d2-79ce82fc65df.png)

In this code, an array named numbers contains five integers:var numbers = [1,2,3,4,5];. Let's break down the rest of the code in more detail:

* The numbers array calls the map() method.
* Inside the map() method, there is another function. This function is anonymous, meaning that the function does not have a name. When map() is called, it in turn calls this anonymous function.
* The anonymous function takes a parameter, named num, and returns the number multiplied by 2. Its sole task is to perform this single action.
* For every element in the array, the map() method calls the anonymous function, which doubles the value of the element.
* The map() method returns an array of doubled values, which is assigned the variable doubled.
Here, the map() function becomes a method of the numbers array. It then takes in an anonymous function whose sole task is to double the value of num, its argument.

Behind the scenes, an iterative process similar to a for loop takes place. The anonymous function takes in each integer of the numbers array and doubles it. Finally, the variable doubled is an array of integers whose values are twice their original values.

Try running the code in your browser console and view the results for doubled. You should see the following:

![Screenshot_20221122_015004](https://user-images.githubusercontent.com/107443962/203428399-88dd308f-3b9f-40ac-b04f-e09d05c598de.png)

## The filter() Method
Another functional programming technique is the filter() method. Like the map() method, it accepts another function as its parameter. Like map(), filter() performs an operation on every element in the original array. Unlike map(), however, filter() does not necessarily return an array whose length is the same as the original array.

Let's see what this means in an example. Run the following code in your console. What does larger return?

![Screenshot_20221122_015059](https://user-images.githubusercontent.com/107443962/203428542-cc5bc758-0453-4d5c-988c-587fee223cee.png)

It returns an array of integers that are larger than 1: [2,3,4,5].This example is remarkably similar to the last one, with one major difference.

First, the similarities:

* The numbers array uses the filter() method.
* The filter() method, in turn, takes an anonymous function as its argument. The anonymous function's sole task is to take in a parameter, called num.
* The filter() method operates on each element of the numbers array. So how does it differ from map()?

The map() method transforms every element of the original array, and so the size of the transformed array is the same as that of the original array.

The filter() method, on the other hand, returns an array of values that meet certain criteria. Values in the original array that do not fulfill the condition are filtered out. In this case, specifically, the anonymous function called by filter() returns true if an argument is larger than 1, and false if it does not. The filter() method runs the anonymous function on every element of the original numbers array. Only numbers that are larger than 1 are returned: [2,3,4,5]. So whereas applying map() to the numbers array would have returned an array with five elements, applying this specific filter returned an array of only four elements.

## The Arrow Functions
Let's do a quick review of arrow functions. An arrow function in JavaScript is syntactic sugar. That is, an arrow function does the same thing as a standard JavaScript function, but it streamlines the syntax used to accomplish the same task.

The anonymous function inside map() and filter() can be simplified as an arrow function. Here's an example:

![Screenshot_20221122_015416](https://user-images.githubusercontent.com/107443962/203429076-63ea2bfa-78f3-4cfc-b666-86bed8d75e79.png)

The map() method performs the identical operation as before: it doubles each element in the numbers array. However, the anonymous function inside map() has been replaced by an arrow function. Contrast the two:

![Screenshot_20221122_015454](https://user-images.githubusercontent.com/107443962/203429184-3ff1199f-084b-44ac-aee6-48a15b5370ed.png)

sortedAge returns the array [2,3,9,37,39]. Like map() and filter(), sort() takes in an anonymous function. During each iteration, the anonymous function, an arrow function in this case, compares one element of the array (a) with another element in the array (b). From a, it subtracts b. If the result is negative (i.e., b is larger than a) then it stays put. If the result of the subtraction is positive, the order of the two elements is reversed. Look at a modified version of this example.

The slice() Method
Roza also needs to be able to select a subset of the data. In her project, for example, she might perform a transformation on an array, filter it, sort it, and then display only the top five results.

![Screenshot_20221122_015601](https://user-images.githubusercontent.com/107443962/203429370-0a711dc8-7495-4285-829d-9ced5d94e163.png)

In this example, the slice() method returns the first two elements of the integer array: [0,1]. The first argument is the position of where to begin the selection. Here, it is at index position 0. The next argument, 2, denotes the position of the array where the slicing ceases. In other words, the slice() method begins selecting the array at index position 0, and stops right before reaching index position 2. So here, it returns elements at index positions 0 and 1, but not 2.

Deliverable 1:
Create a Horizontal Bar Chart
Deliverable Requirements:
Using your knowledge of JavaScript, Plotly, and D3.js, create a horizontal bar chart to display the top 10 bacterial species (OTUs) when an individual’s ID is selected from the dropdown menu on the webpage. The horizontal bar chart will display the sample_values as the values, the otu_ids as the labels, and the otu_labels as the hover text for the bars on the chart.

Your bar chart should look like the following image:

![Screenshot_20221122_015707](https://user-images.githubusercontent.com/107443962/203429588-5f54a1b3-358c-4d7e-8cac-95d970c85e4d.png)

1. Code is written to create the arrays when a sample is selected from the dropdown menu.
2. Code is written to create the trace object in the buildCharts() function, and it contains the following:
* The y values are the otu_ids in descending order.
* The x values are the sample_values in descending order
* The hover text is the otu_labels in descending order.
3. Code is written to create the layout array in the buildCharts() function that creates a title for the chart.
4. When the dashboard is first opened in a browser, ID 940’s data should be displayed in the dashboard, and the bar chart has the following:
* The top 10 sample_values are sorted in descending order
* The top 10 sample_values as values
* The otu_ids as the labels

## Results with detail analysis:
1. Code is written to create the arrays when a sample is selected from the dropdown menu.
Image with JavaScript & HTML Code below.

Code and Image

![Screenshot_20221122_020002](https://user-images.githubusercontent.com/107443962/203430136-6daeb68b-0758-4eb9-a080-b433e81f63e6.png)

![Screenshot_20221122_021713](https://user-images.githubusercontent.com/107443962/203432559-8652ffc5-bfda-4a13-ab8c-a7fe365e348d.png)

2. ode is written to create the trace object in the buildCharts() function, and it contains the following:
* The y values are the otu_ids in descending order.
* The x values are the sample_values in descending order
* The hover text is the otu_labels in descending order.
Image with JavaScript & HTML Code below.

Code and Image

![Screenshot_20221122_021900](https://user-images.githubusercontent.com/107443962/203432876-76d94409-7a38-4aaa-b305-32d24d412d61.png)

![Screenshot_20221122_021938](https://user-images.githubusercontent.com/107443962/203432949-de4405f6-0326-4e3c-82d8-1856141a8af9.png)

3. Code is written to create the layout array in the buildCharts() function that creates a title for the chart.

Code and Image

![Screenshot_20221122_022030](https://user-images.githubusercontent.com/107443962/203433074-b195f025-aeaa-40e3-9274-ad382cbc5051.png)

![Screenshot_20221122_022044](https://user-images.githubusercontent.com/107443962/203433106-a0189382-3620-4ff9-8d50-5dcc6f03de9d.png)

4. When the dashboard is first opened in a browser, ID 940’s data should be displayed in the dashboard, and the bar chart has the following:
* The top 10 sample_values are sorted in descending order
* The top 10 sample_values as values
* The otu_ids as the labels
Image with JavaScript & HTML Code below.

Code and Image

![Screenshot_20221122_022236](https://user-images.githubusercontent.com/107443962/203433460-65da837c-6006-4418-9244-c6a76cf9cae7.png)

![Screenshot_20221122_022434](https://user-images.githubusercontent.com/107443962/203433683-2d6d93e0-1d3a-4000-956d-19df7b144f50.png)

# Deliverable 2:
## Create a Bubble Chart
## Deliverable Requirements:
Using your knowledge of JavaScript, Plotly, and D3.js, create a bubble chart that will display the following when an individual’s ID is selected from the dropdown menu webpage:

* The otu_ids as the x-axis values.
* The sample_values as the y-axis values.
* The sample_values as the marker size.
* The otu_ids as the marker colors.
* The otu_labels as the hover-text values.
Your bubble chart should look like the following image:

![Screenshot_20221122_022608](https://user-images.githubusercontent.com/107443962/203433895-6833c2d3-bed9-40b7-ac40-bed27c65f32e.png)

1.  code for the trace object in the buildCharts(); function does the following:
* Sets the otu_ids as the x-axis values
* Sets the sample_values as the y-axis values
* Sets the otu_labels as the hover-text values
* Sets the sample_values as the marker size
* Sets the otu_ids as the marker colors
2.  code for the layout in the buildCharts(); function does the following:
* Creates a title
* Creates a label for the x-axis
* The text for a bubble is shown when hovered over
3. When the dashboard is first opened in a browser, ID 940’s data should be displayed in the dashboard. All three charts should also be working according to their requirements when a sample is selected from the dropdown menu

## Results with detail analysis:
1.  code for the trace object in the buildCharts(); function does the following:
* Sets the otu_ids as the x-axis values
* Sets the sample_values as the y-axis values
* Sets the otu_labels as the hover-text values
* Sets the sample_values as the marker size
* Sets the otu_ids as the marker colors
Image with JavaScript & HTML Code below.

Code and Image

![Screenshot_20221122_023207](https://user-images.githubusercontent.com/107443962/203434792-e0f36b9b-4773-4f37-b238-79becb8d1f77.png)

![Screenshot_20221122_023219](https://user-images.githubusercontent.com/107443962/203434809-9907f7be-6d3c-4f26-a857-4a7d03dc51e4.png)

2.  code for the layout in the buildCharts(); function does the following
* Creates a title
* Creates a label for the x-axis
* The text for a bubble is shown when hovered over.

Code and image

![valle_nevado](https://user-images.githubusercontent.com/107443962/203435102-7c9b84a7-2843-4b73-b72f-8a0e5c348375.png)

![Screenshot_20221122_023444](https://user-images.githubusercontent.com/107443962/203435163-81d164a9-e4a6-48cb-ad06-0e64aa602fc4.png)

3. When the dashboard is first opened in a browser, ID 940’s data should be displayed in the dashboard. All three charts should also be working according to their requirements when a sample is selected from the dropdown menu.

Code and image 

![Screenshot_20221122_023544](https://user-images.githubusercontent.com/107443962/203435279-a5752431-018a-4785-9c92-4f52ad9532d5.png)

![Screenshot_20221122_023612](https://user-images.githubusercontent.com/107443962/203435377-209a7921-ea9b-4f01-940f-0bb31c5e8802.png)

# Deliverable 3
## Create a Gauger Chart
## Deliverable Requirements

Using your knowledge of JavaScript, Plotly, and D3.js, create a gauge chart that displays the weekly washing frequency's value, and display the value as a measure from 0-10 on the progress bar in the gauge chart when an individual ID is selected from the dropdown menu.

Your gauge chart should look similar to the following image:

![Screenshot_20221122_023803](https://user-images.githubusercontent.com/107443962/203435596-88d62500-a6b8-4d99-b2e0-9ef31b9b0725.png)

1. The code to build the gauge chart does the following: 
* Creates a title for the chart.
* Creates the ranges for the gauge in increments of two, with a different color for each increment.
* Adds the washing frequency value on the gauge chart.
* The indicator shows the level for the washing frequency on the gauge.
* The gauge is added to the dashboard.
* The gauge fits in the margin of the <div> element.

2. When the webpage loads, the bar and bubble chart are working according to the requirements in Deliverable 1 and 2, respectively, and the gauge chart is working according to the requirements listed for this Deliverable

## Results with detail analysis:

1. The code to build the gauge chart does the following:
* Creates a title for the chart.
* Creates the ranges for the gauge in increments of two, with a different color for each increment.
* Adds the washing frequency value on the gauge chart. 
* The indicator shows the level for the washing frequency on the gauge.
* The gauge is added to the dashboard.
* The gauge fits in the margin of the <div> element.

Code and Image 

![Screenshot_20221122_030618](https://user-images.githubusercontent.com/107443962/203439183-32dd1be1-8fc2-44df-89ed-aa11795249bf.png)

![Screenshot_20221122_030633](https://user-images.githubusercontent.com/107443962/203439214-053147ea-92b8-4916-911b-26dff213b2b4.png)

![Screenshot_20221122_030701](https://user-images.githubusercontent.com/107443962/203439278-1653b30c-9380-4679-9f4f-aefb78205bc5.png)

![Screenshot_20221122_030701](https://user-images.githubusercontent.com/107443962/203439314-3cb6c751-b39a-4262-9106-b8a3797b165f.png)

2. When the webpage loads, the bar and bubble chart are working according to the requirements in Deliverable 1 and 2, respectively, and the gauge chart is working according to the requirements listed for this Deliverable

Code and Image 

![Screenshot_20221122_032424](https://user-images.githubusercontent.com/107443962/203441148-0aee9d50-b232-4d36-aade-d03e6100aa79.png)

![Screenshot_20221122_032513](https://user-images.githubusercontent.com/107443962/203441248-b11b1e87-11a1-4dda-b076-822ef9ed9212.png)

## Deliverable 4

## Customize the Dashboard

Deliverable Requirments:

Use your knowledge of HTML and Bootstrap to customize the webpage for your dashboard
1. Customize your dashboard with three of the following:
* Add an image to the jumbotron.
* Add background color or a variety of compatible colors to the webpage
* Use a custom font with contrast for the colors.
* Add more information about the project as a paragraph on the page.
* Add information about what each graph visualizes, either under or next to each graph.
* Make the webpage mobile-responsive
* Change the layout of the page
* Add a navigation bar that allows you to select the bar or bubble chart on the page.
2. When the dashboard is first opened in a browser, ID 940’s data should be displayed in the dashboard, and the three charts should be working according to their requirements.
3. When a sample is selected, the dashboard should display the data in the panel and all three charts according to their requirements.

## Results with detail analysis

1. Customize your dashboard with three of the following:
* Add an image to the jumbotron.
* Add background color or a variety of compatible colors to the webpage.
* Use a custom font with contrast for the colors.
* Add more information about the project as a paragraph on the page.
* Add information about what each graph visualizes, either under or next to each graph.
* Make the webpage mobile-responsive.
* Change the layout of the page
* Add a navigation bar that allows you to select the bar or bubble chart on the page.

![Screenshot_20221122_033259](https://user-images.githubusercontent.com/107443962/203442025-5caf35ad-69bd-4232-80e9-39427b689635.png)

![Screenshot_20221122_033317](https://user-images.githubusercontent.com/107443962/203442055-654e70d3-7833-40db-9cec-f5080775cfd0.png)

2. When the dashboard is first opened in a browser, ID 940’s data should be displayed in the dashboard, and the three charts should be working according to their requirements.

![Screenshot_20221122_033349](https://user-images.githubusercontent.com/107443962/203442146-b90e11bb-1a56-489c-b846-f18b24c6fafa.png)

3. When a sample is selected, the dashboard should display the data in the panel and all three charts according to their requirements.

![Screenshot_20221122_033431](https://user-images.githubusercontent.com/107443962/203442230-760af872-3845-47ac-8d31-ff71fe752449.png)
