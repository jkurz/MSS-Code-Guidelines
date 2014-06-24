# MSS Code Guidelines
Version 0.11.0


## Contributors
**YOU!** - please contribute to these code guidelines! If you have any
suggestions for improvement to these guidelines, *[create an issue][issue]* to
discuss it or *create a [pull request][pr]* with your changes and discussion
will occur on that PR.


### Original Authors
- James Young [@jamsyoung](http://twitter.com/jamsyoung), [github](https://github.com/jamsyoung)
- Matt Crutchfield [@mtcrutch](https://twitter.com/mtcrutch), [github](https://github.com/mtcrutch)


## JavaScript
The JavaScript guidelines are based off of [idiomatic.js][idiomatic].

For lots of code examples that show the style we want, see the
[airbnb guide][airbnb].

The MSS Guidelines will be the same with the following additional rules applied.


### Test Facility
We will be using:

- Mocha / Chai for unit tests
- Selenium (WebdriverJS) / Mocha / Chai for functional tests
- PhantomJS / CasperJS for functional tests


### Idiomatic Style Manifesto
0. Whitespace
    - 4-space soft indents are required.  This means four spaces or four spaces
      representing a tab.

0. Beautiful Syntax
    - 2.A - 2.C should not have `inner-space`.  Refer to 2.D for a syntax
      without `inner-space`.  Here is an example.
      ```javascript
      function foo(bar, baz) {
          var qux = bar + baz;

          for (i = 0; i < 10; i++) {
              console.log(qux);
          }

          if (bar === baz) {
              qux = bar * baz;
          } else {
              qux = bar / baz;
          }

          return qux;
      }
      ```

    - Single quotes must be used.

    - Object literals should look like this.
      ```javascript
      var objectLiteral;

      objectLiteral = {
          foo: 'bar',
          baz: 'qux'
      };
      ```

    - Milliseconds should be assigned in multiples of 1000, and always use
      explicit order of operations.
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
  `<li>` elements should not be closed. [Further reading on this inline-block
  issue.][inline]


## CSS / Sass
0. The CSS / Sass guidelines are based off of [csswizardry/CSS-Guidelines][css].
0. We use [nomalize.css][normalize] as our style reset.


#### Our CSS / Sass overrides
0. Declarations.
  Declarations should be in aplhabetical order (**NOT** by relevance).


## Markdown
0. All lines that are not code blocks should wrap at or under 80 columns.
0. Should allow trailing whitespace, since that is a valid Markdown syntax.
0. Should have 2 blank lines above each H1 and H2 heading except for the
   heading at the top of the document.  This is optinal for other headings.
0. Should have 4 blank lines to separate the link reference at the bottom of
   the document.
0. Should use `0.` for ordered lists
0. Should use `-` for unordered lists
0. Secondary bullets must be indented four spaces to render correctly on
  Bitbucket.
0. Do not try to put code blocks as secondary bullets in a list.  They will not
  render correctly on both GitHub and BitBucket. More details on this to come
  in the future.


## Changelog

- 0.11.0
  - Added reference to the [airbnb guide][airbnb]
  - Changed title of page to be space delimited, not dash delimited
  - Changed [idiomatic.js][idiomatic] link reference to use a label instead of
    being inline
  - Alphabetized the link references at the bottom of this document
  - Added Markdown section.
  - Changed this document to match the Markdown guidelines.

- 0.10.0
  - Added Changelog and version number

- 0.9.0
  - Added if/else example in JavaScript code example

- 0.8.0
  - Change to Contributors
  - Added Original Authors

- 0.7.1
  - Fixed typo

- 0.7.0
  - Fixed typo
  - Clarity on JavaScript milliseconds
  - More details on HTML for quotes and whitespace

- 0.6.0
  - Changed Maintainers to Contributors
  - Markdown cleanup

- 0.5.0
  - Updates to JavaScript code example
  - Added details for JavaScript object literals
  - Added details for JavaScript milliseconds

- 0.4.0
  - Updates to HTML guidelines
  - Updates to CSS / SASS guidelines

- 0.3.0
  - Added HTML guidelines
  - Added CSS / SASS guidelines

- 0.2.0
  - Added exceptions over idiomatic for unit testing

- 0.1.0
  - Initial version




[airbnb]: https://github.com/airbnb/javascript
[css]: https://github.com/csswizardry/CSS-Guidelines
[idiomatic]: https://github.com/airbnb/javascript
[inline]: http://css-tricks.com/fighting-the-space-between-inline-block-elements/
[issue]: https://github.com/TurnerBroadcasting/MSS-Code-Guidelines/issues/new
[normalize]: http://necolas.github.io/normalize.css/
[pr]: https://github.com/TurnerBroadcasting/MSS-Code-Guidelines/compare/
