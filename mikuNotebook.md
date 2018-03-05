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
Created the test workflow earlier in the week before receiving some real data later in the week.



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
I think that my third seminar presentation was my best one yet. Once again, people gave me valuable feedback and suggestions. One of my classmates informed me that hourly data can be compared in Google Sheets so RegExp is not necessary. Seeing as I can't get RegExp to work in the Script editor, I will give this a try.



### February 27, 2018
Went to SPI to see data input process
- Lots of issues with the database
