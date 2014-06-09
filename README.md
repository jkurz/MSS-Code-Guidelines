# MSS-Code-Guidelines

## Maintainers
* James Young [@jamsyoung](http://twitter.com/jamsyoung), [github](https://github.com/jamsyoung)
* Matt Crutchfield [@mtcrutch](https://twitter.com/mtcrutch), [github](https://github.com/mtcrutch)

## JavaScript
The JavaScript guidelines are based off of [idiomatic.js](https://github.com/rwaldron/idiomatic.js).

The MSS Guidelines will be the same with the following additional rules applied.

### Test Facility

We will be using:

* Mocha / Chai for unit tests
* Selenium (WebdriverJS) / Mocha / Chai for functional tests
* PhantomJS / CasperJS for functional tests


### Idiomatic Style Manifesto

1. Whitespace
    * 4-space soft indents are required.  This means four spaces or four spaces representing a tab.

2. Beautiful Syntax
    * 2.A - 2.C should not have `inner-space`.  Refer to 2.D for a syntax without `inner-space`.  Here is an example.
        ```
        function foo(bar, baz) {
            var qux = bar + baz;

            for (i = 0; i < 10; i++) {
                console.log(qux);
        	}
        }
        ```

    * Single quotes must be used.

## HTML

1. Write clean semantic HTML5 markup.  
1. Selectors  
  Never use an ID as a styling hook.  
  Prefix any JavaScript class hooks with `js-`. Example: `class="js-foo foo"`  
1. Closing `<li>` elements.  
  `<li>` elements should not be closed. [Further reading on this inline-block issue.][inline]

## CSS / Sass
The CSS / Sass guidelines are based off of [csswizardry/CSS-Guidelines][css].

### Our overrides

1. Declarations.  
  Declarations should be in aplhabetical order (**NOT** by relevance).

[inline]: http://css-tricks.com/fighting-the-space-between-inline-block-elements/
[css]: https://github.com/csswizardry/CSS-Guidelines
