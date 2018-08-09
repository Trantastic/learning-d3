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
d3.select()  
d3.selectAll()

All selection methods return a new selection. Meaning you can only make a new one and overwrite it. You can't modify it. 

Selections are objects. You can chain selects together:
	var allGroups = d3.selectAll("g");
	var allCircles = d3.selectAll("circle");
	var allCirclesInGroups. d3.selectAll("g").selectAll("circle");

	simplify => var allCirclesInGroups = d3.selectAll("g circle");