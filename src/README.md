## Website Performance Optimization portfolio project

The fifth project in the Udacity Front End Web Developer Nanodegree program was to optimize a portfolio website. The first part requires to optimize the PageSpeed Insights score for index.html to 90 or higher. The second requires to optimize the pizza.html to run at a consisten 60fps, and have the pizzas resize at under 10ms.

## Usage

To run the site open the file index.html. PageSpeed Insights score of 96 on mobile and 97 on desktop

## Gulp usage

The task runner Gulp has been used to optimize the site.

Type the following commands into your command line in the root directory (where gulpfile.js is located). All working files are located in the 'src' directory, and running gulp tasks will output to the 'dist' directory.

gulp sass
Compiles any sass files into css files.

gulp scripts
Concatenates & minifies JavaScript files into all.js and all.min.js. Gzip functionality currently commented out.

gulp html
Minifies and inlines any associated CSS files. Gzip functionality currently commented out.

gulp styles
Minifies CSS files. Gzip functionality currently commented out.

gulp images
Minifies images.

gulp scripts-views, gulp html-views, gulp styles-views, gulp images-views
Run the same tasks as above but in the views directory. Necessary to keep directory structure for reviewers.

gulp watch
Watches for changes in any of the above files and runs associated tasks.

gulp
Runs all of the above.

## Pizza page optimizations

Now running at a steady 60fps! Resizing the pizzas using the slider now takes about 1ms!

### 'Movers' elements

* Reduced number of mover elements created from 200 to 25.
* Added the backface-visibility: hidden CSS attribute to force them into seperate composite layers. This meant that the browser wasn't required to paint the whole page each time the element moved.
* Subtracted half the window width from the basicLeft variable for use in the updatePositions function.

### updatePositions function

* Replaced querySelectorAll with getElementsByClassName which is considerably faster.
* Removed from the for loop the calculation to find scrollTop divided by 1250, and an array of values for use in the phase calculation.
* Stored the variable items.length outisde of the loop (attribute to http://www.html5rocks.com/en/tutorials/speed/html5/)
* Replaced the CSS style 'left' which triggers layout, paint and composite, with transform, which only triggers composite. Found on csstriggers.com. The syntax for this can be attributed to Udacity user 'mcs' (https://discussions.udacity.com/t/project-4-how-do-i-optimize-the-background-pizzas-for-loop/36302).

#### requestAnimationFrame

* Used requestAnimationFrame to run the updatePositions function at a steady rate.
* Added a running variable to ensure requestAnimationFrame did not run after scrolling was completed.
(attribute to https://www.kirupa.com/html5/animating_with_requestAnimationFrame.htm)

### resizePizzas function

* Instead of calculating the size difference when resizing, I used the switch statement to return a percentage based on the size value.
* Said percentage was then used in the changePizzaSizes function as the width attribute of the pizza containers.
* Replaced querySelectorAll with getElementsByClassName which is considerably faster.

Useful tips helped me get started:

1. Check out the repository
1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ngrok http 8080
  ```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)

Profile, optimize, measure... and then lather, rinse, and repeat. Good luck!

####Part 2: Optimize Frames per Second in pizza.html

To optimize views/pizza.html, you will need to modify views/js/main.js until your frames per second rate is 60 fps or higher. You will find instructive comments in main.js. 

You might find the FPS Counter/HUD Display useful in Chrome developer tools described here: [Chrome Dev Tools tips-and-tricks](https://developer.chrome.com/devtools/docs/tips-and-tricks).

### Optimization Tips and Tricks
* [Optimizing Performance](https://developers.google.com/web/fundamentals/performance/ "web performance")
* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")
* [Optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html "optimize the crp!")
* [Avoiding Rendering Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html "render blocking css")
* [Optimizing JavaScript](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript.html "javascript")
* [Measuring with Navigation Timing](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp.html "nav timing api"). We didn't cover the Navigation Timing API in the first two lessons but it's an incredibly useful tool for automated page profiling. I highly recommend reading.
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads.html">The fewer the downloads, the better</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer.html">Reduce the size of text</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization.html">Optimize images</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching.html">HTTP caching</a>

### Customization with Bootstrap
The portfolio was built on Twitter's <a href="http://getbootstrap.com/">Bootstrap</a> framework. All custom styles are in `dist/css/portfolio.css` in the portfolio repo.

* <a href="http://getbootstrap.com/css/">Bootstrap's CSS Classes</a>
* <a href="http://getbootstrap.com/components/">Bootstrap's Components</a>

### Sample Portfolios

Feeling uninspired by the portfolio? Here's a list of cool portfolios I found after a few minutes of Googling.

* <a href="http://www.reddit.com/r/webdev/comments/280qkr/would_anybody_like_to_post_their_portfolio_site/">A great discussion about portfolios on reddit</a>
* <a href="http://ianlunn.co.uk/">http://ianlunn.co.uk/</a>
* <a href="http://www.adhamdannaway.com/portfolio">http://www.adhamdannaway.com/portfolio</a>
* <a href="http://www.timboelaars.nl/">http://www.timboelaars.nl/</a>
* <a href="http://futoryan.prosite.com/">http://futoryan.prosite.com/</a>
* <a href="http://playonpixels.prosite.com/21591/projects">http://playonpixels.prosite.com/21591/projects</a>
* <a href="http://colintrenter.prosite.com/">http://colintrenter.prosite.com/</a>
* <a href="http://calebmorris.prosite.com/">http://calebmorris.prosite.com/</a>
* <a href="http://www.cullywright.com/">http://www.cullywright.com/</a>
* <a href="http://yourjustlucky.com/">http://yourjustlucky.com/</a>
* <a href="http://nicoledominguez.com/portfolio/">http://nicoledominguez.com/portfolio/</a>
* <a href="http://www.roxannecook.com/">http://www.roxannecook.com/</a>
* <a href="http://www.84colors.com/portfolio.html">http://www.84colors.com/portfolio.html</a>
