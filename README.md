# learning-d3
*These are my notes while learning D3.js*

# Starting
Grab the CDN: [https://d3js.org/]

	<!DOCTYPE html>
	<html>
	<head>
		<title>D3.js Bar Chart</title>
		<script src="https://d3js.org/d3.v5.min.js"></script>
	</head>

# Selections
`d3.select()` => selects a specific element or the first of that element  
`d3.selectAll()` => selects ALL elements that match

All selection methods return a new selection. Meaning you can only make a new one and overwrite it. You can't modify it. 

Selections are objects. You can chain selects together:

	var allGroups = d3.selectAll("g");
	var allCircles = d3.selectAll("circle");
	var allCirclesInGroups. d3.selectAll("g").selectAll("circle");

	simplify => var allCirclesInGroups = d3.selectAll("g circle");

# Dealing with missing data
`.define()` => checks if the value exists and returns true or false

`.define((d) => d)` => if d exists return true, if doesn't exist return false

To exclude a value, if you know a value is N/A or an invalid value:

	var line = d3.line()
				 .defined((d) => d.average >= 0;) //if false, the value will be thrown out
				 .x((d) => xScale(d.date))
				 .y((d) => yScale(d.average));