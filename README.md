# BUILD-TOOLS-BUCHELI-COURSE-PROJECT-ROCK-PAPER-BUNDLE

# Off-Platform Project: Rock, Paper, Bundle

## Configure an existing web application to use Webpack.

## Part 1 - Configuring the Node Project
Let’s get started by initializing the Node project using the default values.

Hint
Use the npm init command with the -y flag.


Next, define the build and start commands in the scripts section of package.json. build should run webpack --watch and start should run webpack serve --open. These will allow 
us to bundle and view our project.

Hint
Inside the scripts section of our package.json, we want build to run webpack --watch and start to run webpack serve --open.

We define custom commands through the syntax:

scripts: {
    "customCommand" : "commandsToRun"
}

The commands and loaders don’t come with npm init. We are going to need to install the npm packages our project needs as developer dependencies:

webpack
webpack-cli
webpack-dev-server
style-loader
css-loader
Hint
To install packages, we use npm install <packagename>. Save all of these as developer dependencies by using the --save-dev flag.

## Part 2 - Configuring Webpack
Time to start setting up Webpack!

Create a Webpack configuration file, and set the mode to development.

Hint
Create a webpack.config.js file and define the module.exports with mode set to development inside of it.


Next, add rules in the config file for CSS, fonts, and images. We will be using .css for our CSS, .woff and .woff2 file types for our fonts, and .png for our images.

Hint
We will need at least 2 rules (fonts and images can be the same rule).

Rules typically have a test attribute and either a use or type attribute. Check out the [Building Apps with Webpack Lesson](LINK TO ADD) for the exact syntax.


Uh oh! This project’s code isn’t saved in the typical place for a Webpack project. Let’s make sure Webpack can find the code we want to bundle. Define the entry point according to where the code for the project is stored.

Hint
The main JavaScript file is in the code folder and is named main.js. An entry point can be defined in the config file with:

entry: 'path/to/file.js'

## Part 3 - Bundling the CSS
With Webpack, we can include CSS through our JavaScript!

Delete the link in the head tag of the HTML, and import the CSS within main.js using the Webpack syntax.

Hint
With Webpack, we can import CSS within JavaScript using the following syntax:

import './example.css';
Don’t forget to delete the link in the HTML.

## Part 4 - Bundling the JavaScript
Managing a bunch of <script> tags in HTML can get messy in a big project. Let’s simplify!

With Webpack, we are only going to need one <script> tag in our HTML. First, delete the existing <script> tags. Then add one that embeds the JavaScript code that will be at our exit point.

Hint
The <script> tag will be similar to those already in the file, but it will point to our exit point, dist/main.js.


Then, we need to link all our JavaScript content using import and export statements.

Add export statements to code/util.js and code/game.js, exporting the functions contained in the files.

Hint
At the bottom of code/util.js and code/game.js, export the content defined in the file.For example:

function hello() {
  console.log(`Hello World!`);
}
 
export { hello };

Finally, import the functions we just exported into code/main.js.

Hint
At the top of code/main.js use the ES6 import syntax to import from the util and game files. It should look something like below:

import {content_name1} from 'path_to_file1';
import {content_name2} from 'path_to_file2';

## Part 5 - Bundling Images
Time to import some images!

Import the Scissors, Rock, and Paper icons from the asset folder using the Webpack syntax, and replace their URLs in the makeChoiceImage with the named import values.

Hint
We import an image in our JavaScript with syntax like:

import Square from '../square.png';
Once imported, we can use the image as a variable:

img.src = Square;

## Part 6 - Building and Viewing Our App
We are ready to launch our project!

Navigate two terminal windows to the project directory. Then run the build command in one and start in the other. We should be able to open up our preview and see the result!

Hint
To run a custom command we use:

npm run <command>
Review
Congratulations! You just added Webpack to an existing project to build the app! In this project, we were able to take an existing codebase and add in a Webpack configuration that bundles its fonts, images, and CSS.

Now you can build your own web apps using Webpack in your local environment!

```
npm install --save-dev webpack webpack-cli webpack-dev-server style-loader css-loader
```

```
npm run build
```

```
npm run start
```

