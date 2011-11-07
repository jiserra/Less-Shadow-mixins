#Less Shadow Mixins

##What?

It's a Mixin library for [LESS](http://lesscss.org/) to use CSS Drop shadows without images. The shadows are based on the excellent [CSS code by Nicolas Gallagher](http://nicolasgallagher.com/css-drop-shadows-without-images/)

Here you can see a [demo of the shadows](http://nicolasgallagher.com/css-drop-shadows-without-images/demo/).

##How?

To use it first include the mixins on your less file:

	@import "shadows.less";

If you just import the mixins, nothing will happen, no code is added to your final css file. To use a shadow, you have to add it like this.

	.box {
		#shadow > .lifted();
	}

And that's it! Your class box now has a shadow on it!

As always, be careful not to overuse shadows! Don't include more than one or two styles, you could bloat your stylesheet easily.

Also, if you plan to use one type of shadow on different elements, **don't do this:**
	
	.element {
      #shadow > .lifted();
	  background-color: red;
	}
	.another_element {
	  #shadow > .lifted();
	  background-color: blue;
	}

Instead, group the classes that use the same shadow and declare the differences later, like you would normally do with CSS. Why? Because LESS doesn't support extending so you end up duplicating your styles. **Do this instead:**

	.element, .another_element {
      #shadow > .lifted();
	}
	.element {
	  background-color: red;
	}
	.another_element {
	  background-color: blue;
	}

##Demo

You can see a demo of the mixins in action in the `demo-shadows.html` file.

**Happy Shadowing!**
