# Contributing

Please do! You could add documentation, fix bugs, add to the demos/integrate
with other elm-libraries, or add components. There are opportunities for 
both newcomers and experienced Elm programmers: adding documentation, fixing
bugs and adding missing features is a good way to get deeper into the language; 
for experienced programmers, every step of the way (so far) has for me been 
a surprisingly subtle and complex challenge in finding proper APIs. 

## Adding documentation 

This is perhaps the easiest place to start. In some cases, documentation can be 
based more or less directly on the 
[MDL documentation](getmdl.io/components). In other cases, you'll need to read
the code needing documentation. If you are new to Elm, this could be a good way
to get deeper into the language. 

 - The
   [Snackbar](https://github.com/debois/elm-mdl/blob/master/src/Material/Snackbar.elm)
   is functional but has no documentation. 
   ([Issue](https://github.com/debois/elm-mdl/issues/9).) 
 - Demo pages need intro text a la MDL docs. 
   ([Issue](https://github.com/debois/elm-mdl/issues/8).) 

See the [documentation issue
list](https://github.com/debois/elm-mdl/issues?utf8=%E2%9C%93&q=is%3Aissue+label%3Adocumentation+)

## Enhancing/fixing existing components

Some components are stable but not fully featured. Adding minor features could be a 
good way to get started. 

See the [enhancement issue
list](https://github.com/debois/elm-mdl/issues?utf8=%E2%9C%93&q=is%3Aissue+label%3Aenhancement).

## Improving demos / Integration with other libraries

If you have some experience with other Elm packages, it'd be very interesting to see
if the library interacts properly with these.  Right now, 

 - The
   [Snackbar](https://github.com/debois/elm-mdl/blob/master/src/Material/Snackbar.elm)
   could do with more animation, and it'd be very interesting to see if the library
   interacts reasonably with elm-html-animation. 
   ([Issue](https://github.com/debois/elm-mdl/issues?utf8=%E2%9C%93&q=is%3Aissue+label%3Ademo).)

  - The main tabs should be connected to a router, so that the url reflects the current tab. 
  ([Issue](https://github.com/debois/elm-mdl/issues/7).)

See the [demo issue list](https://github.com/debois/elm-mdl/issues?utf8=%E2%9C%93&q=is%3Aissue+label%3Ademo).

## Contributing components

The easiest place to start is to add more CSS-only components. These
require no porting of Javascript, just putting together css-classes as
instructed by the 
[MDL Component Documentation](https://www.getmdl.io/components/index.html). 
These components invariably require serious thinking about what is an
appropriate Elm API and so are usually interesting in their own right for 
that reason.  Take a look at

  
 - [Cards](https://www.getmdl.io/components/index.html#cards-section) [Work-in-progress: [Håkon Rossebø](https://github.com/hakonrossebo])]
 - [Dialogs](https://www.getmdl.io/components/index.html#dialog-section)
 - [Footers](https://www.getmdl.io/components/index.html#layout-section/footer)
 - [Lists](https://www.getmdl.io/components/index.html#lists-section) [Work-in-progress: [Håkon Rossebø](https://github.com/hakonrossebo])]
 - [Shadows](https://github.com/google/material-design-lite/tree/v1.1.2/src/shadow)

Progress bars are pure CSS, and spinners seem to use Javascript only to insert
auxiliary DOM-nodes on initialisation.

 - [Loading](https://www.getmdl.io/components/index.html#loading-section)

The remaining components, use Javascript
in various ways. Toggles seem to use Javascript exclusively to insert ripple-animations and __might__ be easy to implement using the `Ripple.elm`
component:

 - [Toggles](https://www.getmdl.io/components/index.html#toggles-section)

The rest I haven't looked at; they may or may not be straightforward to port
to Elm.

 - [Tables](https://www.getmdl.io/components/index.html#tables-section)
 - [Sliders](https://www.getmdl.io/components/index.html#sliders-section)
 - [Menus](https://www.getmdl.io/components/index.html#menus-section)
 - [Snackbars](https://www.getmdl.io/components/index.html#snackbar-section) [Work-in-progress]
 - [Tooltips](https://www.getmdl.io/components/index.html#tooltips-section)

### Getting started with a new component

Each component has its actual code in `src/Material/NameOfComponent.elm` and a demo in 
`examples/Demo/NameOfComponent.elm`. These are what you need to construct.
To get started quickly, do this:

1. Clone this repository
2. Copy the file `src/Material/Template.elm` to `src/Material/NameOfYourComponent.elm`. Rename
as appropriate in the file. 
3. Copy the file `examples/Demo/Template.elm` to `examples/Demo/NameOfYourComponent.elm`. 
Rename as appropriate in the file. 
4. In `examples/Demo.elm`, find all the places that mentions `template` or `Template`, 
copy those bits, and rename as appropriate. 
5. Compile and open `page.html` in a browser.

The last tab contains your component. Now all you need is code!

To avoid duplication of work, 
[open an issue](https://github.com/debois/elm-mdl/issues/new) and let everybody know
that you are working on a particular component. 
