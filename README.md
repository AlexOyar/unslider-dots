# Responsive SlideShow using Unslider Dots

In this tutorial we will be making a full responsive slideshow using dots as indexes with Unslider.
Then, we will add some text on top of the images and set some cool Jquery animations to them. 

Notice that in this tutorial i will not add a navigation bar, if you want to see how to make a full responsive navigation
bar, i will upload one later.

The first thing we will do i to set up our project structure and dependencies, for that i will use two different tools,

1. Node.JS NPM : NPM or Node package manager, allows you to install several tools or dependencies. Dont worry about what that means you will know in a minute.
2. Bower : Bower is as well a package manager but is generally used not to install tools but dependencies, like CSS or JS libraries/modules.

**WHY?**

Well, It is posible to add your dependencies by yourself without these tools, and that's fine. But if you are serious about web development, you will notice that it is incredibly easy to add any package/module/library you want using Bower. And we need Node.JS NPM in order to install it. More information about bower [here] (https://bower.io/) and Node.JS [here] (https://nodejs.org/en/)

- First, install Node.JS by downloading the installer in their web page, after following instructions make sure is properly set up by opening you command shell (CMD in windows) and typing `npm -v`, you should be able to see your current npm version.

- Great! now we can install bower using npm. Now just type `npm install -g bower` this means: Hey! install bower in my machine, globally using npm.

- Finally, for this tutorial we will be using Unslider and Jquery. Navigate to your project folder directory in the command shell and then type the following command: `bower install jqery` and `bower install unslider`, notice that a new bower_components folder will be added to your project. Inside that folder you will find any package that you will install.

**Now we are set and we can start doing cool stuff.**

First, in your directory create your index.html and add the following code:

<script src="https://gist.github.com/AlexOyar/ad907d335f24a530c1ca01ab2706dee9.js"></script>

I already added the CSS dependencies in the Head and the Scripts (jquery and unslider) an the bottom of the Body. JQUERY MUST BE FIRST THAN UNSLIDER OTHERWISE IT WONT WORK.


Example of a basic slideshow with dots index using unslider

