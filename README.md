# Responsive SlideShow using Unslider Dots

In this tutorial we will be making a full responsive slideshow using dots as indexes with **Unslider** and some titles.

Notice that in this tutorial i will not add a navigation bar, if you want to see how to make a full responsive navigation
bar, i will upload one later.

The first thing we will do i to set up our project structure and dependencies, for that i will use two different tools,

1. Node.JS NPM : NPM or Node package manager, allows you to install several tools or dependencies. Dont worry about what that means you will know in a minute.
2. Bower : Bower is as well a package manager but is generally used not to install tools but dependencies, like CSS or JS libraries/modules.

**WHY?**

*Well, It is posible to add your dependencies by yourself without these tools, and that's fine. But if you are serious about web development, you will notice that it is incredibly easy to add any package/module/library you want using Bower. And we need Node.JS NPM in order to install it. More information about bower [here] (https://bower.io/) and Node.JS [here] (https://nodejs.org/en/)*

- First, install Node.JS by downloading the installer in their web page, after following instructions make sure is properly set up by opening you command shell (CMD in windows) and typing `npm -v`, you should be able to see your current npm version.

- Great! now we can install bower using npm. Now just type `npm install -g bower` this means: Hey! install bower in my machine, globally using npm.

- Finally, for this tutorial we will be using Unslider and Jquery. Navigate to your project folder directory in the command shell and then type the following command: `bower install jqery` and `bower install unslider`, notice that a new bower_components folder will be added to your project. Inside that folder you will find any package that you will install.

**Now we are set and we can start doing cool stuff.**

First, in your directory create your index.html and add the following code:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Unslider Dots</title>
    <!--CSS Dependencies-->
    <link rel="stylesheet" href="bower_components/unslider/dist/css/unslider-dots.css" media="screen" title="no title">
    <link rel="stylesheet" href="bower_components/unslider/dist/css/unslider.css" media="screen" title="no title">
    <link rel="stylesheet" href="css/style.css" media="screen" title="no title">
    <style media="screen">
    .unslider {
        /* new */
        overflow: hidden;
        position: relative;
    }
    .unslider-nav{
            position: absolute;
            width: 100%;
            bottom: 2%;
      }
      body{
        background-color: rgb(43, 43, 43)
      }
    </style>
  </head>
  <body>
    <section>
      <div class="banner">
        <ul>
          <li style="background-image: url('http://placehold.it/1280x750');">
            <div class="slideanim">
              <h1>A great title for this slideshow.</h1>
              <br>
              <p>Lorem ipsum dolor sit amet, quo lorem ignota id, homero consectetuer pro te.</p>
              <p>Cum eu dolores periculis. Prompta repudiandae te eum, id sea aliquip scriptorem.</p>
              <br>
              <a class="btn" href="#">See more</a>
            </div>
          </li>
          <li style="background-image: url('http://placehold.it/1280x750');">
            <div class="slideanim">
              <h1>The perfect title for your second image.</h1>
              <br>
              <p>Lorem ipsum dolor sit amet, quo lorem ignota id, homero consectetuer pro te.</p>
              <p>Cum eu dolores periculis. Prompta repudiandae te eum, id sea aliquip scriptorem.</p>
              <br>
              <a class="btn" href="#">Check it out</a>
            </div>
          </li>
          <li style="background-image: url('http://placehold.it/1280x750');">
            <div class="slideanim">
              <h1>Another awesome title for the last one.</h1>
              <br>
              <p>Lorem ipsum dolor sit amet, quo lorem ignota id, homero consectetuer pro te.</p>
              <p>Cum eu dolores periculis. Prompta repudiandae te eum, id sea aliquip scriptorem.</p>
              <br>
              <a class="btn" href="#">Take me there</a>
            </div>
          </li>
        </ul>
      </div>
    </section>
    <script src="bower_components/jquery/dist/jquery.min.js"></script>
	  <script src="bower_components/unslider/dist/js/unslider-min.js"></script>
    <script>
		jQuery(document).ready(function($) {
			var slider = $('.banner').unslider({
        dots: true,
        nav:true,
        fluid: true,
        infinite: true 		//Repeats the slideshow after last slide
      });
      //  Listen to changes
      slider.on('unslider.change', function(event, index, slide) {
        //Here trigger any event when unslider changes
      });
		});
	</script>
  </body>
</html>
```

**The trick here is that in order to work, you must add a few parameter to `unslider` class, like `overflow: hidden; position: relative;`**

That means that we will make some changes to the original css files from unslider. I dont know why do we have to do this manually, but simply putting dots:true inside the unslider script wont work.

*I already added the CSS dependencies in the Head and the Scripts (jquery and unslider) an the bottom of the Body. JQUERY MUST BE FIRST THAN UNSLIDER OTHERWISE IT WONT WORK.*

Now, you can see that the background image is not properly scaling, the font is default black, and the link is just a... well... a link. So, in order to make it pretty, just add the style.css.  

Add a new css folder and create the following style.css:

```css

* {
	margin: 0;
	padding: 0;
	-webkit-font-smoothing: antialiased;
	-webkit-box-sizing: border-box;
	-moz-box-sizing: border-box;
	box-sizing: border-box;
}

.banner
{
  position:relative;
  width:100%;
  overflow:hidden;
  font-size:18px;
  line-height:24px;
  color:rgba(255,255,255,.6);
  text-shadow:0 0 1px rgba(0,0,0,.05), 0 1px 2px rgba(0,0,0,.3);
  box-shadow:0 1px 2px rgba(0,0,0,.25);
}

.banner ul
{
  list-style:none;
  width:300%;
}

@media screen and (min-width: 768px){
  .banner ul li
  {
    min-height: 300px;
		display: table
  }
}
@media screen and (min-width: 1024px){
  .banner ul li
  {
    min-height: 350px;
		display: table
  }
}
@media screen and (min-width: 1366px){
  .banner ul li
  {
    min-height: 400px;
		display: table
  }
}
@media screen and (min-width: 1600px){
  .banner ul li
  {
    min-height: 500px;
		display: table
  }
}
@media screen and (min-width: 1900px){
  .banner ul li
  {
    min-height: 600px;
		display: table
  }
}
@media screen and (max-width: 500px){

}

.banner ul li
{
  float:left;
  width:33%;
  -moz-background-size:100% 100%;
  -o-background-size:100% 100%;
  -ms-background-size:100% 100%;
  background-size: 100% 100%;
  box-shadow:inset 0 -3px 6px rgba(0,0,0,.1);
  padding:16px 0 110px;
  width: 100%;
  height: auto;
	display: table;
}

.banner ul li div {
	display: table-cell;
	vertical-align: middle;
	padding-left:10%;
	padding-top: 100px;
}

.banner h1,.banner h2
{
  font-size:4em;
  line-height:52px;
  color:#fff;
}

.banner p
{
	font-size:1.3em;
  color:#fff;
}

.banner .btn
{
  display:inline-block;
  clear:both;
  color:#fff;
  font-size:1em;
  font-weight:700;
  text-transform:uppercase;
  text-decoration:none;
  border:2px solid rgba(255,255,255,.4);
  border-radius:5px;
  margin:25px 0 0;
  padding:15px 27px 13px;
}

.banner .btn:hover
{
  background:rgba(255,255,255,.5);
}

.banner .btn:active
{
  -webkit-filter:drop-shadow(0-1px2pxrgba(0,0,0,.5));
  -moz-filter:drop-shadow(0-1px2pxrgba(0,0,0,.5));
  -ms-filter:drop-shadow(0-1px2pxrgba(0,0,0,.5));
  -o-filter:drop-shadow(0-1px2pxrgba(0,0,0,.5));
  filter:drop-shadow(0-1px2pxrgba(0,0,0,.5));
}

.banner .btn,.banner .dot
{
  -webkit-filter:drop-shadow(01px2pxrgba(0,0,0,.3));
  -moz-filter:drop-shadow(01px2pxrgba(0,0,0,.3));
  -ms-filter:drop-shadow(01px2pxrgba(0,0,0,.3));
  -o-filter:drop-shadow(01px2pxrgba(0,0,0,.3));
  filter:drop-shadow(01px2pxrgba(0,0,0,.3));
}

.banner .dots
{
  position:absolute;
  left:0;
  right:0;
  bottom:20px;
}

.banner .dots li
{
  display:inline-block;
  width:10px;
  height:10px;
  text-indent:-999em;
  border:2px solid #fff;
  border-radius:6px;
  cursor:pointer;
  opacity:.4;
  -webkit-transition:background .5s, opacity .5s;
  -moz-transition:background .5s, opacity .5s;
  transition:background .5s, opacity .5s;
  margin:0 4px;
}

.banner .dots li.active
{
  background:#fff;
  opacity:1;
}

```

