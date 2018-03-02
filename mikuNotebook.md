### Miku Fukuyama
Scmp 401 Notebook :notebook:

#### January 30, 2018
Met with Professor Glandon and Bennett to discuss project ideas.

Meeting notes:
- Stock returns are forecastable in the medium to long run
- Use the latest thinking on forecasting future distribution of returns
  - Use price-earnings ratio of market and some measure of volatility
  - Write a function that takes starting value, number of years to simulate, expected returns, and standard deviation of returns as inputs. Output is a vector of length n where n is the number of years to simulate with each row corresponding to a year in the future.
- Will be using Python



#### February 3, 2018
Met with the director of SPI Spot, Rachel Garcia, to discuss a potential project.



#### February 4, 2018
Met with Professor Garcia to go over the M.O. and proposal for the SPI workflow project.
- Will create workflow using Google Sheets and its functions, Google Apps Script, and Google Sheets pivot table interface



#### February 5, 2018
Seminar Presentation #1

*Reflection:*
My first seminar presentation was pretty stressful, as I am really not good at public speaking. However, I believe that public speaking is a crucial skill to have and hope to improve with each presentation throughout the semester.
Before my next presentation (which is next class), I am going to email Rachel a list of fields that I think should be included in the workflow and ask if she can send me some data to work with. I also plan on making a test workflow in Google Sheets to familiarize myself with Google Sheets and its functions, pivot tables, and Google Apps Script, as well as to determine how I will utilize these resources in the actual workflow.


#### Week of February 5, 2018
Created the test workflow earlier in the week before receiving some real data later in the week.



#### February 12, 2018
Seminar Presentation #2

*Reflection:*
I think that my second seminar presentation went much better than my first, and I think it was because I had a better understanding of what my project entailed this time around. I think the informal format of the presentation also helped me to be less nervous. I liked that people were able to chime in and offer feedback and suggestions, and ask thought-provoking questions that I had not even thought of, many of which I plan to ask Rachel sometime this week.



#### Week of February 19, 2018
Goals before next presentation:
- Aggregate and normalize age data
- Normalize hourly data


Aggregating and normalizing age data:

*Version 1 (Static)*

Counting number of children that are 1:

=COUNTIF(Sheet1!E2:J526, "1")

Use same formula for ages 2-12+

Problem: what if number of entries changes?

*Version 2 (Dynamic)*

Counting number of children that are 1:

Where E2=526,

="Sheet1!E2:J"&E2 //call this dynamicRange

=COUNTIF(indirect(dynamicRange), "1")


#### February 26, 2018
Seminar Presentation #3

*Reflection:*
I think that my third seminar presentation went better than any of my other presentations. I felt slightly more comfortable speaking, and again, people gave very helpful feedback and gave me ideas that I had never thought of. I was having a lot of trouble normalizing the time data using regex, but one of my classmates informed me that hourly data can be compared in Google sheets so that regex would not be necessary.
