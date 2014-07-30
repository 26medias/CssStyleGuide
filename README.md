# CSS Style guide #

When writting HTML/CSS code, having working code is simply not enough. There are unofficial rules that should be respected.

*   Your code needs to be formatted properly. 
*   Your code should use LessCss or Sass, not pure CSS.
*   Your code should be isolated in its own scope.
*   Your code should be flexible. A simple change shouldn't lead to a large chunk being rewritten.
*   Your code should be commented when necessary.
*   Your code should be easy to read and understand by another developer.
*   Your code should be factorized whenever possible.
*   Your code should be done based on the intent, not just the specs.

### Your code needs to be formatted properly. ###

Here is an example of code that is unreadable, hard to edit and nearly impossible to understand without spending a lot of time on it:
```
#testi {background: #ececfb; padding: 44px 0; padding-bottom: 70px; text-align: center; position: relative; /*z-index: -1;*/}
#testi .testi_holder {}
#testi .testi_holder .left {padding: 0 10px 0 40px;}
#testi .testi_holder .right {padding: 0 30px 0 10px;}
#testi .testi_holder .right .voice {}
#testi .testi_holder .right .voice .top {text-align: left;}
#testi .testi_holder .right .voice .mid {padding-top: 10px; padding-bottom: 10px; padding-left: 50px; padding-right: 35px; text-align: left;}
#testi .testi_holder .right .voice .mid h3 {font-family: 'aleolightitalic'; font-size: 22px; color: #737384; margin-bottom: 30px;}
#testi .testi_holder .right .voice .mid p {margin: 0; font-family: 'aleoitalic'; font-size: 16px; line-height: 1.5; color: #737384;}
#testi .testi_holder .right .voice .bottom {text-align: right; margin-bottom: 30px;}
#testi .testi_holder .right .voice .authur {}
#testi .testi_holder .right .voice .authur .name {text-align: right; font-family: 'aleolightitalic'; font-size: 14px; color: #9797a5; line-height: 1.6; padding-top: 35px;}
#testi .testi_holder .right .voice .authur .name span {font-family: 'aleoitalic'; font-size: 14px; display: block;}
#testi .testi_holder .right .voice .authur .name a {color: #9797a5;}
#testi .testi_holder .right .voice .authur .pic {text-align: center;}
#testi #myCarousel2 {position: relative;}
#testi .carousel-indicators {position: relative; display: inline-block; top: 445px;}
#testi .carousel-indicators li    {	background-color: #fff; border: 2px solid #B9B9C8; width: 15px; height: 15px; cursor: pointer; margin-left: 25px;
								border-radius: 10px; -moz-border-radius: 10px; -webkit-border-radius: 10px; }
#testi .carousel-indicators .active {background-color: #ffa64d;}
```
That type of formatting is fine for production, but is **really bad practice** when you have other people working on the code.

A developer wouldn't be able to just read the code abnd understand whét's goign on, and where to edit to achieve a particular result. it forces to unfold the code and reformat manually to finally understand what's going on and edit.

Now let's see that same code simply re-formatted:
```
#testi {
    background: 		#ececfb;
	padding: 			44px 0;
	padding-bottom: 	70px;
	text-align: 		center;
	position: 			relative;
	/*z-index: -1;*/
}
#testi .testi_holder {

}
#testi .testi_holder .left {
	padding: 			0 10px 0 40px;
}
#testi .testi_holder .right {
	padding: 			0 30px 0 10px;
}
#testi .testi_holder .right .voice {

}
#testi .testi_holder .right .voice .top {
	text-align: 		left;
}
#testi .testi_holder .right .voice .mid {
	padding-top: 		10px;
	padding-bottom: 	10px;
	padding-left: 		50px;
	padding-right: 		35px;
	text-align: 		left;
}
#testi .testi_holder .right .voice .mid h3 {
	font-family: 		'aleolightitalic';
	font-size: 			22px;
	color: 				#737384;
	margin-bottom: 		30px;
}
#testi .testi_holder .right .voice .mid p {
	margin: 			0;
	font-family: 		'aleoitalic';
	font-size: 			16px;
	line-height:		1.5;
	color: 				#737384;
}
#testi .testi_holder .right .voice .bottom {
	text-align: 		right;
	margin-bottom: 		30px;
}
#testi .testi_holder .right .voice .authur {

}
#testi .testi_holder .right .voice .authur .name {
	text-align: 		right;
	font-family: 		'aleolightitalic';
	font-size: 			14px;
	color: 				#9797a5;
	line-height: 		1.6;
	padding-top: 		35px;
}
#testi .testi_holder .right .voice .authur .name span {
	font-family: 		'aleoitalic';
	font-size: 			14px;
	display: 			block;
}
#testi .testi_holder .right .voice .authur .name a {
	color: 				#9797a5;
}
#testi .testi_holder .right .voice .authur .pic {
	text-align: 		center;
}
#testi #myCarousel2 {
	position: 			relative;
}
#testi .carousel-indicators {
	position:			relative;
	display: 			inline-block;
	top: 				445px;
}
#testi .carousel-indicators li	{
	background-color: 	#fff;
	border: 			2px solid #B9B9C8;
	width: 				15px;
	height: 			15px;
	cursor: 			pointer;
	margin-left: 		25px;
	border-radius: 		10px;
	-moz-border-radius: 10px;
	-webkit-border-radius: 10px;
}
#testi .carousel-indicators .active {
	background-color: 	#ffa64d;
}
```

That code is much easier to read! In an instant you can see what the code is doing, you can easily understand where are the classnames, where are the properties and where are the values.

A developer wouldn't have to spend much time to understand what's going on and where to edit to achieve a particular goal.

#### Formatting rules ####
Every developer and company has its own formatting rules, but here are the 3 rules you can't go wrong with.

*   Put all the classnames on a single line: `#testi .carousel-indicators li {`
*   Put **only one** property per line.
*   Separate the properties and values, align all the values using tabs. it makes them much faster to read.

*Note: Do not use spaces to separate the values. They make it easy to mess up the formatting. Always use tabs, as they always align perfectly. A tab should be setup to take the size of 4 spaces, which is the international standard (text editor settings)*


### Your code should use LessCss or Sass, not pure CSS. ###
Tools like LessCss were developed to help developers be more efficient while providing a lot more flexibility and making their code easier to read and update.

You should always develop using LessCss or a similar tech, and compile to CSS only for the production.

Let's take the same code as before, but simply rewrite it in LessCss to make it even easier to read and edit.

```
#testi {
    background:	 	    #ececfb;
	padding: 			44px 0;
	padding-bottom: 	70px;
	text-align: 		center;
	position: 			relative;
	.testi_holder {
		.left {
			padding: 			0 10px 0 40px;
		}
		.right {
			padding: 			0 30px 0 10px;
			.voice {
				.top {
					text-align: 		left;
				}
				.mid {
					padding-top: 		10px;
					padding-bottom: 	10px;
					padding-left: 		50px;
					padding-right: 		35px;
					text-align: 		left;
					h3 {
						font-family: 		'aleolightitalic';
						font-size: 			22px;
						color: 				#737384;
						margin-bottom: 		30px;
					}
					p {
						margin: 			0;
						font-family: 		'aleoitalic';
						font-size: 			16px;
						line-height:		1.5;
						color: 				#737384;
					}
				}
				.bottom {
					text-align: 		right;
					margin-bottom: 		30px;
				}
				.authur {
					.name {
						text-align: 		right;
						font-family: 		'aleolightitalic';
						font-size: 			14px;
						color: 				#9797a5;
						line-height: 		1.6;
						padding-top: 		35px;
						span {
							font-family: 		'aleoitalic';
							font-size: 			14px;
							display: 			block;
						}
						a {
							color: 				#9797a5;
						}
					}
					.pic {
						text-align: 		center;
					}
				}
			}
		}
	}
	#myCarousel2 {
		position: 			relative;
	}
	.carousel-indicators {
		position:			relative;
		display: 			inline-block;
		top: 				445px;
		li {
			background-color: 	#fff;
			border: 			2px solid #B9B9C8;
			width: 				15px;
			height: 			15px;
			cursor: 			pointer;
			margin-left: 		25px;
			border-radius: 		10px;
			-moz-border-radius: 10px;
			-webkit-border-radius: 10px;
		}
		.active {
			background-color: 	#ffa64d;
		}
	}
}
```

As you can see, that code is even easier to read, making the life of any developer that needs to edit that code much easier.
But there are still issues with that code, mainly scope issues, which brings us to the next point.

### Your code should be isolated in its own scope. ###

Imagine You want to apply that style to more than one element on the page.
Since the css only apply to elements that have the id #testi, and since DOM IDs are unique, that means that this code can apply to only one element per page. It's entire scope is reduced to a single element, that can't be duplicated. That's a serious limitation.

As a general rule, CSS should never target DOM IDs. It's very unflexible.

But that's not the only issue with the code.

The code here setup some classnames that are really common, like `.top`, `.bottom`, `.active`, ...

Let's take the example of one of the last line, `#testi .carousel-indicators .active`.

If you have that code, then it's all good:
```
<div id="testi">
    <div class="carousel-indicators">
		<div class="active"></div>
	</div>
</div>
```

But watch what happens if the HTML even gets edited like this:
```
<div id="testi">
    <div class="carousel-indicators">
		<div class="active"></div>
		<div class="someOtherClass">
			<div class="somethingElse">
				<div class="active"></div>
			</div>
		</div>
	</div>
</div>
```

Because of the way the CSS is written, the `.active` whose parent is `.somethingElse` will inherit the style setup by `#testi .carousel-indicators .active`, because that notation doesn't limit the style to only the immediate children of `#testi .carousel-indicators`, it applies the `.active` style to **ANY** of the descendant, even way down the line. And because `active` is a really common name, the chances of the `#testi .carousel-indicators .active` style overwritting another style is very likely, making the code incompatible with 3rd party libraries like Bootstrap for example, or with other developers' code that might also implement a `.active` className.

The correct way to write that particular style would be to apply `.active` **only** to the immediate child of `#testi .carousel-indicators`, which is done simply by using a CSS combinator, in that case, the child combinator `>`. Example:
`#testi .carousel-indicators > .active`, or in lessCss: 
```
#testi {
    .carousel-indicators {
        & > .active {
            ...
        }
    }
}
```

Learning to use CSS combinators is extremely important and can't be skipped.

Mozilla Developer Network explains them very well, just scroll the page to **Selectors**:
<https://developer.mozilla.org/en-US/docs/Web/CSS/Reference>


W3.org also have a useful list of selectors: <http://dbjpq4m8xws63.cloudfront.net/gallery/image/growing-up-is-realizing-that>.


#### Isolating the scope ####

It's really important to isolate the scope of your code.

When developping HTML/CSS elements, you always need to assume the style will be updated, duplicated, mixed up with other styles.

For that reason, your style need to be completely isolated and have zero chance of interfering with other styles on the page.

That's why isolating the scope of your style is so important.

Isolating your scope means having a common classname to all of your styles, the classname having a name that is unlikely to be used by anybody else. That means no common names.

If in your styles you use some child-styles using common names like "active" for example, you need to "lock" that style using a CSS combinator, so that the style won't apply to an unlimited number of childrens.


### Your code should be flexible. A simple change shouldn't lead to a large chunk being rewritten. ###

Web projects are never static. They change, they evolve, and as a result the code needs to be updated. For that reason, CSS code must be flexible from the start.

Let's use an example, a simple menu bar:
![Header](http://i.imgur.com/GA9V5Ex.png)

When you write the CSS and HTML structure for that, you need to assume the colors might be changed, the icons might be changed, more menu items might be added... You need to plan for changes.

For that reason, your code needs to be easy to understand and edit by another developer.

```
<!--
    We use a unique name ".pagevamp-navbar" at the base of the code. 
    If it was named simply ".navbar", then the chance to have another style
    having the same name is high, creating potential interferences.
-->

<div class="pagevamp-navbar">
    <div class="logo"></div>
    <ul class="menu">
    	<li>
    		<a href="#" class="icon icon-check">Select Category</a>
    	</li>
    	<li>
            <!--
                If a menu item is active, all the developer has to do is add the class ".active" to the element.
                CSS takes care of the rest.
                Any change of state should always be done by simply adding or removing a single classname.
                If a change of state (active/inative) requires to change the HTML, or edit more than one classname, then the code is probably wrong.
            -->
    		<a href="#" class="active icon icon-02">Choose Bundle</a>
    	</li>
    	<li>
    		<a href="#" class="icon icon-03">Customize</a>
    	</li>
    	<li>
    		<a href="#" class="icon icon-04">Publish</a>
    	</li>
    </ul>
</div>
```

```
/* Import the font */
@import "http://fonts.googleapis.com/css?family=Oswald";

/*
.pagevamp-navbar is the scope of the menu.
If it was named simply .navbar, then the chance to have another style
having the same name is high, creating interferences.
*/
.pagevamp-navbar {
    
	/* Define the colors and main styles in variables */
	@bgColor:		#272C43;
	@textColor:		#ffffff;
	@fontSize:		14px;
	@height:		60px;
	
	/* Apply the font to all the sub elements */
	* {
		font-family: 'Oswald', sans-serif;
	}
	
	background-color:	@bgColor;
	padding:			0 20px;
	height:				60px;
	
	/* Notice the "& >", which means that even is there are other elements on the page using class="logo", as long as their direct parent is not ".pagevamp-navbar", that style won't apply. */
	& > .logo {
		background-position:	left center;
		background-repeat:		no-repeat;
		background-image:		url('images/logo.png');
		width:					30px;
		height:					100%;
		float:					left;
	}
	& > ul.menu {
		float:				right;
		list-style:			none;
		margin:				0;
		padding:			0;
		height:				@height;
		
		& > li {
			display:		table-cell;
			height:			@height;
			padding:		0 8px;
			
			& > a {
				text-decoration:	none;
				line-height:	@height;
				height:			@height;
				display:		block;
				color:			fadeout(@textColor, 60%);	/* We use LessCss functions to make it easier to modify colors, alphas, grandients... */
				font-size:		@fontSize;
				
				&.active {
					color:		@textColor;
				}
				
				/* All icons have the same basic styles including background-position and background-repeat, so we group it that way... */
				&.icon {
					background-position:	left center;
					background-repeat:		no-repeat;
					padding-left:			18px;
				}
				
				/* ...then we define each icon in a way that would make fast and easy for any developer to add more icon choices later.  */
				&.icon-check {
					background-image:			url('images/check_inactive.png');
					
					/* Each icon has 2 states, one active and one non-active. We're grouping the 2 images in the same code block, to make it easier to read and update. */
					&.active {
						background-image:		url('images/check.png');
					}
				}
				&.icon-01 {
					background-image:			url('images/01_inactive.png');
					&.active {
						background-image:		url('images/01.png');
					}
				}
				&.icon-02 {
					background-image:			url('images/02_inactive.png');
					&.active {
						background-image:		url('images/02.png');
					}
				}
				&.icon-03 {
					background-image:			url('images/03_inactive.png');
					&.active {
						background-image:		url('images/03.png');
					}
				}
				&.icon-04 {
					background-image:			url('images/04_inactive.png');
					&.active {
						background-image:		url('images/04.png');
					}
				}
			}
		}
		
	}
}
```


### Your code should be factorized whenever possible. ###
You can't factorize your code in pure CSS, but you can when you use LessCss.

Factorizing your code means creating functions, or as they are called in LessCss, Mixins.

You setup code you reuse a lot in functions, with parameters, and then use those functions/mixins in your code.

Let's take a basic example, let's do this:

![Example](http://i.imgur.com/EH4jilP.png)

**HTML**
```
<div class="demo01"></div>
<div class="demo02"></div>
<div class="demo03"></div>
```

**Pure CSS**
```
.demo01 {
    width: 400px;
	height: 200px;
	display: inline-block;
	margin: 20px;
	border: 1px solid #000000;
	-webkit-border-radius: 0 0 20px 20px;
	-moz-border-radius: 0 0 20px 20px;
	border-radius: 0 0 20px 20px;
	background-color: #272c43;
	background-image: -webkit-linear-gradient(top, #272c43, #556091);
	background-image: -moz-linear-gradient(top, #272c43, #556091);
	background-image: -o-linear-gradient(top, #272c43, #556091);
	background-image: -ms-linear-gradient(top, #272c43, #556091);
	background-image: linear-gradient(top, #272c43, #556091);
	-webkit-box-shadow: 2px 2px 5px #000000;
	-moz-box-shadow: 2px 2px 5px #000000;
	box-shadow: 2px 2px 5px #000000;
}
.demo02 {
	width: 200px;
	height: 200px;
	display: inline-block;
	margin: 20px;
	border: 1px solid #000000;
	-webkit-border-radius: 0 20px 0 20px;
	-moz-border-radius: 0 20px 0 20px;
	border-radius: 0 20px 0 20px;
	background-color: #ffcc00;
	background-image: -webkit-linear-gradient(left, #ffcc00, #b20000);
	background-image: -moz-linear-gradient(left, #ffcc00, #b20000);
	background-image: -o-linear-gradient(left, #ffcc00, #b20000);
	background-image: -ms-linear-gradient(left, #ffcc00, #b20000);
	background-image: linear-gradient(left, #ffcc00, #b20000);
	-webkit-box-shadow: 0 0 10px #ff0000;
	-moz-box-shadow: 0 0 10px #ff0000;
	box-shadow: 0 0 10px #ff0000;
}
.demo03 {
	width: 100px;
	height: 100px;
	display: inline-block;
	margin: 20px;
	border: 1px solid #ffffff;
	-webkit-border-radius: 5px 5px 5px 5px;
	-moz-border-radius: 5px 5px 5px 5px;
	border-radius: 5px 5px 5px 5px;
	background-color: #919ca4;
	background-image: -webkit-linear-gradient(top, #919ca4, #73818a);
	background-image: -moz-linear-gradient(top, #919ca4, #73818a);
	background-image: -o-linear-gradient(top, #919ca4, #73818a);
	background-image: -ms-linear-gradient(top, #919ca4, #73818a);
	background-image: linear-gradient(top, #919ca4, #73818a);
	-webkit-box-shadow: 0 0 4px rgba(0, 0, 0, 0.5);
	-moz-box-shadow: 0 0 4px rgba(0, 0, 0, 0.5);
	box-shadow: 0 0 4px rgba(0, 0, 0, 0.5);
}
```

That's a lot of code, and most of it is pretty much the same, just with different values! Good luck editing.

Let's simplify using LessCSS.


**LessCss**
```
/* This is a function/mixin */
.border-radius-custom (@topleft: 5px, @topright: 5px, @bottomleft: 5px, @bottomright: 5px) {
    -webkit-border-radius: @topleft @topright @bottomright @bottomleft;
	-moz-border-radius: @topleft @topright @bottomright @bottomleft;
	border-radius: @topleft @topright @bottomright @bottomleft;
}
.box-shadow (@x: 0px, @y: 3px, @blur: 5px, @color: #000000) {
	-webkit-box-shadow: @x @y @blur @color;
	-moz-box-shadow: @x @y @blur @color;
	box-shadow: @x @y @blur @color;
}
.gradient (@origin: left, @start: #ffffff, @stop: #000000) {
	background-color: @start;
	background-image: -webkit-linear-gradient(@origin, @start, @stop);
	background-image: -moz-linear-gradient(@origin, @start, @stop);
	background-image: -o-linear-gradient(@origin, @start, @stop);
	background-image: -ms-linear-gradient(@origin, @start, @stop);
	background-image: linear-gradient(@origin, @start, @stop);
}

.demo01 {
	width:		400px;
	height:		200px;
	display:	inline-block;
	margin:		20px;
	border:		1px solid #000000;
	.border-radius-custom(0, 0, 20px, 20px);
	.gradient(top, #272C43, #556091);
	.box-shadow(2px, 2px, 5px, #000000);
}

.demo02 {
	width:		200px;
	height:		200px;
	display:	inline-block;
	margin:		20px;
	border:		1px solid #000000;
	.border-radius-custom(0, 20px, 20px, 0);
	.gradient(left, #ffcc00, #B20000);
	.box-shadow(0, 0, 10px, #ff0000);
}

.demo03 {
	width:		100px;
	height:		100px;
	display:	inline-block;
	margin:		20px;
	border:		1px solid #ffffff;
	.border-radius-custom();
	.gradient(top, #919CA4, #73818A);
	.box-shadow(0, 0, 4px, rgba(0,0,0,0.5));
}
```


### Your code should be done based on the intent, not just the specs. ###

This one is a quick but important one.

Let's re-use the navbar example:

![Header](http://i.imgur.com/GA9V5Ex.png)

A bad developper would look at the design and try to make it look perfect, but only as long as there's not a single change.

Maybe he'd export the icons in JPEG, leaving the blue background color, making it impossible to change the background-color for the whole navbar.

Maybe he'd plan the width of each menu item perfectly based ont he design, making it impossible to add a single letter without having a line-break.

Maybe he's center the text vertically by using a margin-top, making it impossible to simply resize the navbar without having to also edit each link's css.

There are many ways to have a design render perfectly and yet be unusable. And that always happens when developers don't bother to think about the intent of the designer.

You need to plan ahead and imagine what the developper will most likely do with the code.