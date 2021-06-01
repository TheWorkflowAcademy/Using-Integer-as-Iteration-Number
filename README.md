# Using-Integer-as-Iteration-Number
A Deluge script that allows you to use an integer variable to determine the number of times a function should be executed in a loop.

## Core Idea
Suppose you have a function which you want to execute an X number of times in your script, depending on an integer value on a Zoho CRM record. To achieve that, you will need the following things:
* A list variable that acts as an iterator
* A `for each` loop over the list variable above
* A conditional statement in the loop that acts as a controller
* A number variable to count the number of iteration in the loop

## Tutorial

### Create a List Variable as an Iterator
Create a list variable called "iterator" with values from 1 to a number significantly greater than the *expected* count of result pages. If you don't want to type this list by hand, see the [Pinetools Number List Generator](https://pinetools.com/generate-list-numbers). In the example below, we use 20.

```javascript
iterator = [0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,1,17,18,19,20];
```

### Get the Integer Field Value & Set a Counter
* Get the integer value from your record if applicable (this integer will be the number of times the function will be repeated). In this example, we'll just hard-code the integer variable value to 6.
* Set a counter for variable *n* and set it to 0 - this will be used to count the number of iterations.

```javascript
integer = 6;
n = 0;
```

### 'For Each' Loop
Create a `for each` loop that iterates over each index in the *iterator* list variable above.
```javascript
for each i in iterator
{
}
```


### Conditional Statement as Controller & Count the No. of Iteration
* Inside that loop, write a conditional statement to control the number of iteration, and your action script within that condition.
* Set the condition to only allow the script to execute when *n* is lesser than the integer value (in this case, it will make sure that the script will only execute 6 times.
* Below the action script, count the number of iteration by adding 1 to *n*.


```javascript
for each i in iterator
{
	if (n < integer)
	{
		// Write your action script here
    
    // Count the no. of iteration
		n = n + 1;	
	}
}
```
