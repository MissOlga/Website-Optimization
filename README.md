## Website Performance Optimization portfolio project

The fifth project in the Udacity Front End Web Developer Nanodegree program was to optimize a portfolio website. The first part requires to optimize the PageSpeed Insights score for index.html to 90 or higher. The second requires to optimize the pizza.html to run at a consisten 60fps, and have the pizzas resize at under 10ms.

## Usage

To run the site open the file index.html. PageSpeed Insights score of 96 on mobile and 97 on desktop

## Gulp usage

The task runner Gulp has been used to optimize the site.

Type the following commands into your command line in the root directory (where gulpfile.js is located). All working files are located in the 'src' directory, and running gulp tasks will output to the 'dist' directory.

### resizePizzas function

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
At main.js used getElementsByClassName which is a faster API compared to querySelectorAll
