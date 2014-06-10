# MSS-Code-Guidelines


## Contributors
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
        ```javascript
        function foo(bar, baz) {
            var qux = bar + baz;

            for (i = 0; i < 10; i++) {
                console.log(qux);
            }
        }
        ```

    * Single quotes must be used.

    * Object literals should look like this.
        ```javascript
        var objectLiteral;

        objectLiteral = {
            foo: 'bar',
            baz: 'qux'
        };
        ```

    * Milliseconds should be assigned in multiples of 1000, and always use explicit order of operations.
        ```javascript
        var
            oneSecond = 1000 * 1,
            oneMinute = 1000 * 60,
            fiveMinutes = (1000 * 60) * 5;
        ```


## HTML
0. Write clean semantic HTML5 markup.  
0. Use double quotes for attributes.  
0. Use proper indention.
0. Selector Attributes  
  Never use an ID as a styling hook.  
  Prefix any JavaScript class hooks with `js-`. Example: `class="js-foo foo"`  
0. Closing `<li>` elements.  
  `<li>` elements should not be closed. [Further reading on this inline-block issue.][inline]


## CSS / Sass
0. The CSS / Sass guidelines are based off of [csswizardry/CSS-Guidelines][css].
0. We use [nomalize.css][normalize] as our style reset.


#### Our CSS / Sass overrides
0. Declarations.  
  Declarations should be in aplhabetical order (**NOT** by relevance).




[inline]: http://css-tricks.com/fighting-the-space-between-inline-block-elements/
[css]: https://github.com/csswizardry/CSS-Guidelines
[normalize]: http://necolas.github.io/normalize.css/
