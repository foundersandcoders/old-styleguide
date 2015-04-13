# CSS

### SASS

#### IDs
Avoid using ids as much as possible. Ids should only be used if you are absolutely sure that the styling will never be used again on that project. Since, with most projects, this isn't something you can ever by sure of, try using classes and nested elements instead.

#### Nesting
It is tempting to use nesting as an organisational tool. Even though this translates into readable sass, it compiles into unreadable css and it can be difficult to debug.

Only nest if necessary - to make your sass more readable: indent.

When is it necessary to nest?:
if a child element doesn't have its own class or id
When you are using pseudo classes.

If you want an example of how sass should look, practise writing css and compiling it into sass. The end result should be that both documents will be human readable and easy to understand.

For organisation, opt for a modularised file structure instead.

#### File Structure
A file structure based on http://www.sitepoint.com/architecture-sass-project/ is what each FAC project should aim for. That said, for smaller projects less folders and partials are needed. Likewise for larger projects you will likely have to modularise further. The important thing is to have each section of code put in a place that is logical and intuitive to find, even to a newcomer in the project.

Example of a simple, smaller project, file structure:

```
sass/
|
|– base/
|   |– _colour.scss      # colour variables and mixins
|   |– _reset.scss       # Reset/normalize. Should be imported first
|   |– _typography.scss  # Typography rules
|
|– components/
|   |– _buttons.scss     # Buttons styling, mixins and variables
|   |– _carousel.scss    # Carousel styling, mixins and variables
|   |– _dropdown.scss    # Dropdown styling, mixins and variables
|   |– _overlay.scss     # overlay styling, mixins and variables
|   ...                  # Etc…
|
|– helpers/
|   |– _variables.scss   # Generic Sass Variables
|   |– _mixins.scss      # Generic Sass Mixins
|
|– layout/
|   |– _grid.scss        # Grid system //if not using vendor grid system
|   |– _header.scss      # Header styling only
|   |– _footer.scss      # Footer styling only
|   |– _sidebar.scss     # Sidebar styling only
|
|– vendors/
|
`– main.scss             # primary Sass file which includes nothing but @import
```

#### Other Notes:
Avoid using extend directive: Not easy to understand compared to just using a mixin.

#### Best Practices
Take care of using tags unsupported by older browsers
For example, be aware that the vw, vh, vmin, vmaxare, as of late-2014, unsupported by around 20% of browsers. If in doubt, check [Can I use](http://caniuse.com/).

On the whole, use em not px
There is some debate about this, but the weight of opinion is that pixels do not really have much place in modern web design. See, for example [Taking the “Erm..” Out of Ems](http://webdesign.tutsplus.com/articles/taking-the-erm-out-of-ems--webdesign-12321).
