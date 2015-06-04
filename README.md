# MSS Code Guidelines
Version 1.3.1

![I honestly didn't think you could even USE emoji in variable names. Or that there were so many different crying ones.](http://imgs.xkcd.com/comics/code_quality.png)


## Contributors
**YOU!** - please contribute to these code guidelines! If you have any
suggestions for improvement to these guidelines, *[create an issue][issue]* to
discuss it or *create a [pull request][pr]* with your changes and discussion
will occur on that PR.  Also review the [contributing guidelines](guidelines).


### Original Authors
- James Young [@jamsyoung](http://twitter.com/jamsyoung), [github](https://github.com/jamsyoung)
- Matt Crutchfield [@mtcrutch](https://twitter.com/mtcrutch), [github](https://github.com/mtcrutch)


## Conflict Resolution
We have included [JSHint][jshint] and [JSCS][jscs] RC files in this repository
to validate javascript code against these guidelines.  When something is
questioned, these files will always win.  When in doubt, run JSHint and JSCS
with the `.jshintrc` and `.jscsrc` files in place and see if they find any
problems.  It is recommended that you find plugins for your editor of choice to
always validate your code against these files.

### Regarding the multiple suffixed files
There are several `.jscs` and `.jshintrc` files with suffixes in this repo.  It
is up to you to choose the most appropriate one for your project.  Hopefully the
suffixes are clear, but just in case, here are some more details.

- **.jscs**: A JavaScript Code Style config file for ECMAScript 5 code.

- **.jscs-es6**: A JavaScript Code Style config file for ECMAScript 6 code.

- **.jshintrc-browser**: A JS Hint config file for browser based ECMAScript 5
  code.

- **.jshintrc-node**: A JS Hint config file for NodeJS 0.10.x ECMAScript 5 code.

- **.jshintrc-node-es6**: A JS Hint config file for NodeJS 0.11.x+ and IO.js
  ECMAScript 6 code.


## JavaScript
The JavaScript guidelines are based off of [idiomatic.js][idiomatic]. Currently ES5 is supported in all MSS client side applications. ES6 can be written on the server by running node with the harmony flag or using [io.js](https://iojs.org).

* Do not use ES6 for client side applications. Currently ES6 requires transpilation to be ready for production. If you are working on an internal project, then its ok to mess around with ES6. If you do use it, beware you will bleed and feel the side effects of living on the edge.
    * For the daring, check out [jspm](http://jspm.io/), [systemjs](systemjs) and use with either [bable](bable) or [typescript](typescript)

For lots of code examples that show the style we want, see the
[airbnb guide][airbnb].

The MSS Guidelines will be the same with the following additional rules applied.

### Idiomatic Style Manifesto
0. Whitespace
    - 4-space soft indents are required.  This means four spaces or four spaces
      representing a tab.
    - Spaces not Tabs
        - set up your text editor to always convert tabs into spaces
    - EOL 
        - set up your text editor to always have trailing spaces on save

0. Beautiful Syntax
    - 2.A - 2.C should not have `inner-space`.  Refer to 2.D for a syntax
      without `inner-space`.  Here is an example.
      ```javascript
      function foo(bar, baz) {
          var i,
              qux = bar + baz;

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



### Test Facility
Testing is broken out into two parts.

#### Client Side

- [Karma](karma) as the test runner
- [Mocha](mocha) for the test framework
- [Chai](chaijs) for assertions
- [Protractor](protractor) for e2e tests
- PhantomJS / ChromeCanary / Chrome / Firefox / Safari / IE 10 / IE 9 as the supported browsers

Starting a new project
```javascript
    cd $PROJECT
    npm init // follow prompts
    npm install karma --save-dev
    karma init // follow prompts
```

* ES6 code can be written in tests, but it needs to ran through a karma pre-processor. For now just write tests in good old ES5 and lets wait until things stabilize a little before we start using ES6 in tests or any JavaScript we write for that matter.

#### Server Side
- [Mocha](mocha) for the test framework
- [Chai](chaijs) for assertions
- Selenium [WebdriverJS](webdriver) for e2e tests

* Code coverage is not always the goal of projects that we write. Quality tests are more important. When writing tests make sure that all logical pathways are being covered and take the time to dive deep into whatever function is being used. 


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
  Declarations should be in alphabetical order (**NOT** by relevance).


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

[webdriver]: http://webdriver.io/
[typescript]: http://www.typescriptlang.org/
[babel]: https://babeljs.io/
[systemjs]: https://github.com/systemjs/systemjs
[mocha]: http://mochajs.org/
[chaijs]: http://chaijs.com/
[protractor]: https://angular.github.io/protractor/#/
[karma]: http://karma-runner.github.io/0.12/index.html
[guidelines]: https://github.com/TurnerBroadcasting/mss-code-guidelines/blob/master/CONTRIBUTING.md
[airbnb]: https://github.com/airbnb/javascript
[css]: https://github.com/csswizardry/CSS-Guidelines
[idiomatic]: https://github.com/airbnb/javascript
[inline]: http://css-tricks.com/fighting-the-space-between-inline-block-elements/
[issue]: https://github.com/TurnerBroadcasting/MTS-Code-Guidelines/issues/new
[jscs]: https://github.com/mdevils/node-jscs
[jshint]: https://github.com/jshint/jshint/
[normalize]: http://necolas.github.io/normalize.css/
[pr]: https://github.com/TurnerBroadcasting/MTS-Code-Guidelines/compare/
