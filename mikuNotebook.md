### Miku Fukuyama
Scmp 401 Notebook :notebook:

### January 30, 2018
Met with Professor Glandon and Bennett to discuss project ideas.

Meeting notes:
- Stock returns are forecastable in the medium to long run
- Use the latest thinking on forecasting future distribution of returns
  - Use price-earnings ratio of market and some measure of volatility
  - Write a function that takes starting value, number of years to simulate, expected returns, and standard deviation of returns as inputs. Output is a vector of length n where n is the number of years to simulate with each row corresponding to a year in the future.
- Will be using Python



### February 3, 2018
Met with the director of SPI Spot, Rachel Garcia, to discuss a potential project.



### February 4, 2018
Met with Professor Garcia to go over the M.O. and proposal for the SPI workflow project.
- Will create workflow using Google Sheets and its functions, Google Apps Script, and Google Sheets pivot table interface



### February 5, 2018
Seminar Presentation #1

*Reflection:*
My first seminar presentation was pretty stressful, as I am really not good at public speaking. However, I believe that public speaking is a crucial skill to have and hope to improve with each presentation throughout the semester.
Before my next presentation (which is next class), I am going to email Rachel a list of fields that I think should be included in the workflow and ask if she can send me some data to work with. I also plan on making a test workflow in Google Sheets to familiarize myself with Google Sheets and its functions, pivot tables, and Google Apps Script, as well as to determine how I will utilize these resources in the actual workflow.


### Week of February 5, 2018
Created the test workflow earlier in the week before receiving some real data later in the week (data is from the beginning of 2018 to 2/11/18).



### February 12, 2018
Seminar Presentation #2

*Reflection:*
I think that my second seminar presentation went much better than my first, and I think it was because I had a better understanding of what my project entailed this time around. I think the informal format of the presentation also helped me to be less nervous. I liked that people were able to chime in and offer feedback and suggestions, and ask thought-provoking questions that I had not even thought of, many of which I plan to ask Rachel sometime this week.



### Week of February 19, 2018
Goals before next presentation:
- Aggregate and normalize age data
- Normalize hourly data



Aggregating and normalizing age data:

*Version 1 (Static)*

Counting number of children that are 1:
```
=COUNTIF(Sheet1!E2:J526, "1")
```
Use same formula for ages 2-12+

Problem: what if number of entries changes?

*Version 2 (Dynamic)*

Counting number of children that are 1:

Where E2=526,
```
="Sheet1!E2:J"&E2 //call this dynamicRange
=COUNTIF(indirect(dynamicRange), "1")
```
Problems: 
- Director still has to manually input the number of entries (not a huge problem in my opinion)
- Does not count entries that were entered incorrectly
- Not robust



Normalizing hourly data:

Following code works in jsfiddle but not in the Google Script editor

```
var data = `
	1/21/2018 6:00PM
  1/21/2018 7:00PM
  1/21/2018 6:21PM
  1/21/2018 3:00PM
  1/21/2018 6:00PM
  1/21/2018 8:03AM
  1/21/2018 10:21AM
  1/21/2018 10:00AM
  `
  
var arrayData = [];
var data2 = JSON.stringify(arrayData);

// PM Times
var reg6PM = data.match(/6:.*PM/gi).length; //Change data. to data2. if in array. 
var reg7PM = data.match(/7:.*PM/gi).length; //Change data. to data2. if in array.

// AM Times
var reg8AM = data.match(/8:.*AM/gi).length; //Change data. to data2. if in array.
var reg10AM = data.match(/10:.*AM/gi).length; //Change data. to data2. if in array.

console.log("Records between 6:00PM - 7:00PM: " + reg6PM);
console.log("Records between 7:00PM - 8:00PM: " + reg7PM);
console.log("Records between 8:00AM - 9:00AM: " + reg8AM);
console.log("Records between 10:00AM - 11:00AM: " + reg10AM);
```


### February 26, 2018
Seminar Presentation #3

*Reflection:*
I think that my third seminar presentation was my best one yet. Once again, people gave me valuable feedback and suggestions. One of my classmates informed me that hourly data can be compared in Google Sheets (although this turned out not to be true) so RegExp is not necessary. Seeing as I can't get RegExp to work in the Script editor, I will give this a try.



### February 27, 2018
Went to SPI to see data input process
- Lots of issues with the database


*FINISH*


### April 9, 2018
Seminar Presentation #4

*Reflection:*
edit this My goal for my last seminar presentation was to get as much helpful feedback out of my classmates once again. They agreed that the method that I am currently employing to handle daylight savings time was the best way. I just have to write the new function that will address it in the spreadsheet. I also got an idea on how to display the workflow. Kara suggested that I collect all of the relevant information into a separate tab on the spreadsheet so that it is easily viewable for the director. I think that these presentations were a valuable resource, and although they were nervewracking sometimes, they were definitely helpful and my classmates were able to give me a lot of good comments and help the project progress.

### April 16, 2018
This week, drew a UI mockup for the workflow. *insert here*
Figured out what I want for the user in terms of graphics and extractions of the data
Potential issues that may arise...




### April 23, 2018
This week, I had a lot of trouble finalizing the project. There are basic functionality that will be useful to the director. However, certain key aspects still have to be worked out. I have gotten transctions per hour and the number of children coming in as a function of their ages. Those are two that the director wanted. However, I am having trouble figuring out how to get certain fields as a function of time. For example, I would like to have the ages of chidren as a function of time. In other words, I would like to see the number of 1 year olds coming in from 10:11, etc. I would also like to see what time the members of the Sue Family Access Program are coming in. However, this has proved to be much more difficult than I had originally anticipated, due to misunderstandings I had about the built-in functions of Google Sheets. For example, I think it is super annoying that the countifs function has to have the same number of columns over all criteria. Like why is that important if I just want to check whether these things hold and then count the number of times that all of the criteria hold?


### April 30, 2018
I don't think that I will be able to figure out these issues I have been working on for the past few days before tonight's class and I am worried but I'm going to try. I thought I had a brute force way of doing it but there was some circular dependency issue with it and also it's pretty inelegant and really messy. The brute force way was essentially just doing the same thing she does (counting all of the people who are 1 years old in the Age of Child 1 field, in the Age of Child 2 field, etc.) except automating it, which I think is awful.
