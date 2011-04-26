# Stitch CSS Pattern Framework

Patterns are chunks of styles that we use on every project. These chunks of styles generally perform a particular function, such as clearing floats. Having to write these styles each time is annoying and the function of these chunks of code in our stylesheets is obscure. 

By breaking these patterns into reusable classes and mixins we:

* Make our stylesheets free from clutter
* Give our styles more meaning
* Reduce the size of our stylesheet
* Only have to write them once
* Are updatable when newer methods are discovered by updating the framework

# Get It

Install the Rubygem.

````
gem install compass-stitch
```` 

Then in your compass projects, you have access to the patterns. To import all patterns (except the reset) use:

````
@import 'stitch/patterns';
````

At the top of your stylesheet. 

# Patterns

To see all of the patterns available, look at:

https://github.com/anthonyshort/stitch-css/tree/master/stylesheets/stitch/patterns

By using @import 'stitch/patterns'; you will have access to all of the pattern mixins.

# Reset

Stitch includes a CSS reset. This is a new reset I'm working on. It resets everything back to it's raw text form so that it's easy to build from.

View the reset here: https://github.com/anthonyshort/stitch-css/blob/master/stylesheets/stitch/patterns/reset/_desktop.scss

# Helpers

Helpers are parts of code that make writing stylesheets a little bit easier by allowing us to not have to remember chunks of code. Unlike patterns that perform a particular function, helpers just make it easier to do certain things, such as writing prefixed CSS3 properties.

# Project Template

This project folder sets up the conventions for laying out your stylesheets. It is built around the idea that a single site may have many layouts and we'll use media queries to select which layout to use.

However, we don't want to ALWAYS use media queries, so we still have the option to import the layouts statically.

There are two files, master.scss and legacy.scss. Master imports the layouts based on media queries:

````
// Default Layout
@import "layouts/desktop/master.css" screen and (min-width: 481px);

// Adjusted default layout for smaller tablet screens
@import "layouts/tablet/master.css" screen and (min-width: 481px) and (max-width: 1024px);

// Adjusted layout for mobile devices
@import "layouts/mobile/master.css" screen and (max-width: 480px);
````

Whereas the legacy file will import files statically and without media queries. This means we can send the legacy file to browsers that don't support media queries, and we can send the master file to browsers that do.

