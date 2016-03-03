## Website Performance Optimization portfolio project

The fifth project in the Udacity Front End Web Developer Nanodegree program was to optimize a portfolio website. The first part requires to optimize the PageSpeed Insights score for index.html to 90 or higher. The second requires to optimize the pizza.html to run at a consisten 60fps, and have the pizzas resize at under 10ms.

## Usage

To run the site open the file index.html. PageSpeed Insights score of 96 on mobile and 97 on desktop

## Gulp usage

The task runner Gulp has been used to optimize the site.

Type the following commands into your command line in the root directory (where gulpfile.js is located). All working files are located in the 'src' directory, and running gulp tasks will output to the 'dist' directory.

Useful Udacity reviewers' tips helped me update:

### updatePositions function

* Replaced querySelectorAll with getElementById which is considerably faster.
* Removed from the for loop the calculation to find scrollTop divided by 1250, and an array of values for use in the phase calculation.
* Replaced the CSS style 'left' which triggers layout, paint and composite, with transform, which only triggers composite. Found on csstriggers.com. The syntax for this can be attributed to Udacity user 'mcs' (https://discussions.udacity.com/t/project-4-how-do-i-optimize-the-background-pizzas-for-loop/36302).

### resizePizzas function

* Declared the pizzasDiv variable (var pizzasDiv = document.getElementById('randomPizzas');) outside the loop, so the function only makes one DOM call.

* Declared the elem variable (var elem;) outside the loop to prevent it from being created every time the loop is executed.



