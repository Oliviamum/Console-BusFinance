All Challenge 4 documents are saved here Console-BusFinance



Short description explaining the what, why, and how of the project: This project is part of the requirement for the fufillment of the bootcamp project. It is also a practice and demonstration of my understanding of the workings of Javascript fundamentals.

As a new commer to Javascrip, it is important that i understand the functions and how they are used in business analysis 
I have outlined below, a bit of research of my understanding of the the functions and how they are used in the challenge. 

var totalMonths = finances.length;
Explanation: 
This line creates a variable called totalMonths and assigns it the value of the length of the finances array. Since each element of the array corresponds to a month of financial data, this gives the total number of months represented in the data.

var netTotal = 0; 
Explanation: 
This line declares a variable called netTotal and assigns it an initial value of 0. This variable will be used to keep track of the net total amount of profit/losses.

for (var i = 0; i < finances.length; i++) { 
Explanation: 
This line starts a for loop. A for loop is a control flow statement that allows you to execute a block of code repeatedly. The loop runs for as many times as there are items in the finances array.

The var i = 0 initializes a counter variable i to 0. This variable will be used to keep track of the current iteration of the loop.

The i < finances.length condition specifies that the loop should continue running as long as the value of i is less than the length of the finances array.
T
he i++ statement increments the value of i by 1 after each iteration of the loop.
netTotal += finances[i][1]; 

Explanation: 
This line adds the value of the second element ([1]) in the ith item of the finances array to the netTotal variable.
The += operator is a shorthand for adding the value on the right-hand side to the value on the left-hand side, and then assigning the result back to the left-hand side. So, netTotal += finances[i][1] is equivalent to netTotal = netTotal + finances[i][1].

By the end of the loop, the netTotal variable will contain the sum of all the second elements in the finances array. This represents the net total amount of profit/losses.
This code block initializes a variable called netTotal to 0. It then uses a for loop to iterate over each element of the finances array, accessing the second element of each sub-array (which represents the profit/loss amount for that month) and adding it to netTotal. At the end of the loop, netTotal contains the sum of all the profit/loss amounts for all the months in the finances array.

// Calculate the average change in Profit/Losses over the entire period 
var totalChange = 0; 

Explanation: 
This line initializes a variable called totalChange to 0, which will be used to keep track of the total change in profits/losses.

for (var i = 1; i < finances.length; i++) { totalChange += finances[i][1] - finances[i-1][1]; } 

Explanation: 
This for loop goes through each month's financial data and calculates the change in profits/losses from the previous month, and then adds that change to the totalChange variable.

var averageChange = totalChange / (finances.length - 1); 

Explanation: 
This line calculates the average change in profits/losses over the entire period by dividing the totalChange variable by the number of months in the financial data minus one.

// Calculate the average change in Profit/Losses and the total change in profits from month to month var previousProfit = finances[0][1]; var monthlyChanges = []; 

Explanation: 
These two lines initialize two variables: previousProfit is set to the profit/loss value for the first month in the financial data, and monthlyChanges is set to an empty array that will be used to store the monthly changes in profits/losses.

for (var i = 1; i < finances.length; i++) { var currentProfit = finances[i][1]; var change = currentProfit - previousProfit; monthlyChanges.push(change); previousProfit = currentProfit; } 

Explanation: 
This for loop also goes through each month's financial data and calculates the change in profits/losses from the previous month. However, instead of adding these changes to a totalChange variable, it stores each monthly change in the monthlyChanges array. Additionally, it updates the previousProfit variable to the current month's profit/loss value so that it can calculate the change for the next month.

var totalChangeInProfits = monthlyChanges.reduce((a, b) => a + b); 

Explanation: 
This line uses the reduce() method to calculate the sum of all the monthly changes in profits/losses stored in the monthlyChanges array, and stores the result in the totalChangeInProfits variable.

var averageChangeInProfits = totalChangeInProfits / (totalMonths - 1); 

Explanation: 
This line calculates the average change in profits/losses from month to month by dividing the totalChangeInProfits variable by the number of months in the financial data minus one. The totalMonths variable is assumed to be defined elsewhere in the code, and is used to get the total number of months in the financial data.

// Calculate the greatest increase in profits and the corresponding date var greatestIncrease = monthlyChanges.reduce(function(a, b) { return Math.max(a, b); }); 

Explanation: 
This code calculates the greatest increase in profits by using the reduce function, which is used to perform a calculation on an array. In this case, monthlyChanges is an array that contains the difference between the profits in each month. The reduce function takes a function as its argument that compares the previous value (a) with the current value (b) and returns the maximum value. The greatestIncrease variable stores the maximum value returned by the reduce function.

var greatestIncreaseIndex = monthlyChanges.indexOf(greatestIncrease); 

Explanation: 
This code finds the index of the greatest increase in profits by using the indexOf function, which returns the index of the first occurrence of a value in an array. The greatestIncreaseIndex variable stores the index of the maximum value found in the monthlyChanges array.

var greatestIncreaseMonth = finances[greatestIncreaseIndex + 1][0]; 

Explanation: 
This code finds the corresponding month for the greatest increase in profits by using the finances array, which contains the financial data for each month. The greatestIncreaseIndex variable is used to access the month data in the finances array. The greatestIncreaseMonth variable stores the name of the month with the greatest increase in profits.

// Calculate the greatest decrease in losses and the corresponding date var greatestDecrease = monthlyChanges.reduce(function(a, b) { return Math.min(a, b); }); 

Explanation: 
This code calculates the greatest decrease in losses by using the reduce function again, but this time it returns the minimum value instead of the maximum. The greatestDecrease variable stores the minimum value returned by the reduce function.

var greatestDecreaseIndex = monthlyChanges.indexOf(greatestDecrease); 

Explanation: 
This code finds the index of the greatest decrease in losses by using the indexOf function again. The greatestDecreaseIndex variable stores the index of the minimum value found in the monthlyChanges array.

var greatestDecreaseMonth = finances[greatestDecreaseIndex + 1][0]; 
E
xplanation: 
This code finds the corresponding month for the greatest decrease in losses by using the finances array again. The greatestDecreaseIndex variable is used to access the month data in the finances array. The greatestDecreaseMonth variable stores the name of the month with the greatest decrease in losses.

References: 
-Mainly from internet web pages on Javascript