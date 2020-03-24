# Introduction

This document contains the guidelines and best practices for the front end web developers here at the Firm. It describes markup, style and Javascript standards that have, for the most part, become the generally accepted way within the larger development community.

What this document is **not** is a guide on how front end technologies work; a basic familiarity is assumed. It also does not provide evaluations of the pros and cons of various alternatives; when appropriate we pick what we consider to be the best solutions and present them. Issues that don't yet have a clear solution are considered flexible and may or may not be listed.

### Goals

Our motivations in creating this document are to:

-   Foster code consistency across our projects.
-   Facilitate ease of maintenance.
-   Produce code that is less prone to bugs and regressions, is easier to understand and debug.
-   Write code that supports re-use.
-   Work concurrently with multiple devs on the same codebase at the same time in the same way.
-   Guide staff on-boarding or educate new developers.

This document is not intended to replace common sense, conventions requested by particular clients, teams, or prevent expressive or creative solutions to problems. Team or project-specific agreements or client requests will always supersede this document's content.

  

# General Standards

For any project:

-   Consistency and conventions between team members is paramount.
-   Solutions should be as simple and clear as possible.
-   Solutions should serve a specific purpose.
-   Clever code does not mean good code; readability is **critical**

A key hallmark of professional code includes a notion that while we are writing code that must reach a desired goal, we are also creating code that must be read and understood by others.

####  **Code Consistency**
Usage of the same patterns is critical between team members so as to never cause confusion.
It's worth establishing conventions at the project start or enabling automatic settings in the build or editor environments that might enforce particular rules.

    
####  **Indentation**
Please consistently indent, nest, include braces, quotes, and new lines so that code is clear and can be read easily. New code that is added should never deviate from existing formatting conventions or change the indent levels.
For all code languages, we recommend the **use soft tabs** comprised of four spaces per tab. Hitting the Tab key in your text editor should generate four space characters rather than one tab character. This results in our code appearing identical across platforms.
If **tab stops** are favored by a team, simply **maintain consistency** for a project and it's deliverables so developers can make adjustments to their editing environments a **single** time.
    
####  **Readability**
We encourage liberal use of whitespace, comments, and descriptive variable names as appropriate for writing easy-to-read code.

-   There is no need to write code in an obfuscated or compressed way for the purpose of file-size savings.
-   We will use automated server-side or other build processes to optimize files.
-   This includes concatenating files, code minification, gzipping, and setting "Far Future Expires".

The ability for another developer to read the code is paramount above other concerns, especially if optimization can be handled another way.

  

# HTML Markup Best Practices

#### Semantic Markup
HTML provides a number of semantic constructs that allow automated tools like search engines and screen readers to make sense of the document and to understand relationships between pieces of content. Use semantic markup whenever possible — that is to say use elements with specific meanings for specific purposes to convey the spirit of the markup.
A well-written HTML document will make appropriate use of these semantic elements and leave all responsibility for controlling the presentation of the document to the CSS style sheet.

####  **HTML Standards and Browser Support**
All markup will be written using the latest HTML5 markup specifications from the W3C, as implemented by browsers and devices that meet project requirements. When creating markup be sure that the target environments support the techniques being implemented, or that there is a fall-back plan.
There are three primary ways to ensure a modern and consistent experience across all supported platforms in order of complexity:

-   [Normalize](https://github.com/necolas/normalize.css) is a collection of element-specific CSS changes in a single file.
-   [HTML5 polyfill](https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-Browser-Polyfills) or HTML5 Shiv to enable styling and recognition of HTML5 elements in older devices' browsers.
-   [Modernizr](https://modernizr.com/docs)  is a small piece of JavaScript code that automatically detects the availability of next-generation web technologies in your user's browsers.
	
####  **Doctype**
Always include a proper doctype to trigger standards mode. Omitting the doctype [triggers quirks mode](https://developer.mozilla.org/en-US/docs/Quirks_Mode_and_Standards_Mode) and should always be avoided. The HTML5 doctype is simple and easy to remember.
```
	<!doctype html>
```
#### **Character Encoding**
All markup should be delivered as UTF-8, since it has the best support for internationalization. The character encoding should be designated in both the HTTP header and the head of the document via a meta tag. If the server happens to omit the HTTP header, browsers can take a guess at the character encoding and begins parsing and rendering the markup in a particular way. If there are inconsistencies, the browser will re-parse and re-render, throwing away all that work and starting over if it encounters the meta tag and its guess was incorrect. As a best practice, we always put the meta tag as early in the <head> tag as early as possible — however server-settings are ideal.
```
	<meta charset="UTF-8">
```

#### **Optional and Self-closing Tags**
While current standards designate certain closing elements and even document level elements as optional, use all open and closing elements nested in the correct ways to ensure maximum compatibility and clarity of document structure.
Generally speaking, we encourage closing tags and trailing slashes (i.e. XHTML, XML).
```
	<!-- closing "/" is encouraged -->
	<img src="/logo.png" alt="Company" />
	
	<!-- include closing tags  -->
	<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit:</p>
	<ul>
		<li>Vero sunt veritatis magni sit odit</li>
		<li>voluptatum ratione suscipit</li>
	</ul>
```
Unusual markup can lead to bugs in page rendering, DOM interpretation, or even how styles are applied, so it should be avoided.
	
#### **Validation**
Valid markup is necessary not only for better operation and maintenance, it can be an excellent starting place while debugging a page — especially if the problems are unusual. There are many linters, prettyfier and validators, you can start with [W3C Validator](https://validator.w3.org/).

  

#### **Attribute Values**
-   Use quotes to surround all attribute values in HTML, despite quotes being optional in HTML5. This maintains consistency between attribute values that contain whitespace and those that don't.
```
	<form class="form_login module" action="/login" method="POST">
```


# CSS Best Practices

#### **Formatting CSS**
Basic rules for formatting CSS files:
-   Use a new line for every selector and every declaration.
-   Use a single space before the opening brace in a set of rules.
-   Use lowercase for elements and shorthand hex values, e.g., #aaa.
-   Hyphenate class selector names; avoid underscores and camelCase
-   Quote attribute values in selectors
-   Use one level of indentation for each declaration.
-   The closing brace of declaration goes in the same column as the first character of the set of rules.
-   Use a single blank line between sets of rules.

Inside sets of rules or style declarations:

-   Add a single space between the property and value, for example:
-   prop: value; and not prop:value;.
-   Use double quotes for quoted values
-   Always include a semi-colon at the end of the last declaration.
-   Use shorthand if you can, like:
-   padding: 15px 0; and not padding: 15px 0px 15px 0px;
-   When allowed, use 0 without units.

  

-   Putting each selector on its own line and each property on its own line is great for readability and so version control systems can clearly show which parts have changed in a diff.

  

-   **Specificity**
-   Use the minimum specificity required to achieve the desired style. It can be difficult to quickly read and locate styles or even bugs with heavily nested styles in the CSS.
-   Avoid using IDs as they have very high specificity, able to target only one specific element and are hard to override which breaks the cascading nature of a style sheet.

  

-   ```
-   /* BAD */
-   button#back-button { ... }
-   .popular ul li a { ... }
-   .popular > ul > li > a { ... }
-     
    
-   /* GOOD */
-   .popular .nav__listItem { ... }
-   .popular .nav__listItem--open { ... }
-   .popular .nav__buttonBack { ... }
-   ```
-   While performance of CSS selectors has been a debated topic, browsers perform quite well on most types of selectors.
-   As a rule, CSS is most maintainable with the simplest selectors possible. Try applying a class to the element you want to target instead.

  

-   **Do Not Use !important**
-   Avoid using the !important keyword. Treat it like the nuclear option, only to be used in the most extreme of cases. This fundamentally destroys the specificity feature and can even break accessibility for some users.
-   There is usually another way to achieve the same goal without causing headaches for developers in the future who are either trying to debug a styling issue, or trying to use normal specificity to override a style for a particular element only to find that they can't.

  

-   **ID Selectors**
-   As noted above, use the lowest level of specificity necessary to get the desired results. This means the use of the ID selector should be avoided. Often creating a new class is preferable to using inheritance or additional specificity to target an element or elements.
-   ID selectors, if used, should be used mainly as access points for JavaScript or if a very particular use case surfaces. Styles and classes can be applied via the same element with a className.

  

-   **Vendor Prefixes**
-   When using vendor prefixed features, put the standardized rule at the end to ensure browsers optimize and use the standard if they recognize it.
-   ```
-   .accordion__mainPanel {
-   -webkit-transition: all 100ms;
-   transition: all 100ms;
-   }
-   ```
-   **Inline Styling**
-   Do not hard code style information into your HTML markup directly, either with the style attribute that accepts CSS or with deprecated attributes such as align, border, or width. These are difficult to maintain and make it harder to track down what is causing an element to appear as it does.
-   The exact opposite goes to coding email where most of your styles should be inline and use of styling attributes is very important.

  

-   **Box Model**
-   To simplify CSS authoring, we set the box-sizing attribute to border-box for all page elements. This enables us to use round numbers for width like 50% and then apply a padding or border to that same element without needing to

1.  adjust the width accordingly using calc (since borders use pixels rather than percents) or
2.  create an element inside it to take the padding and border. This is the only case where we use the inefficient universal selector (*).

-   ```
-   * {
-   -moz-box-sizing: border-box;
-   -webkit-box-sizing: border-box;
-   box-sizing: border-box;
-   }
-   ```

  

-   **Coding Patterns**
-   There are a number of popular design patterns for naming conventions on selectors, groupings or extensions of styles in CSS files. Sometimes these are of value and may be used on projects as long as the developers are on board and they are used consistently by the team. We recommend [BEM naming convention](http://getbem.com/) for medium to large projects.

  

  

JavaScript Best Practices

  

-   **Inclusion of Code**
-   Use external JavaScript files. **Do NOT include JavaScript in-line in the page unless there is a good reason**.
-   Use the <script> tag to include your JavaScript files at the bottom of your HTML document just before the closing </body> tag. For optimal page performance, concatenate your JavaScript into as few files as possible.

  

-   If the code you are including is not necessary at the time of loading the asynchronous method is preferred.
-   ```
-   <script src="https://cdn.mckinsey.com/assets/example/javascript.js" async defer></script>
-   ```
-   In development environments, this may point at a non-optimized file, however having techniques in place to toggle optimized files on and off is often beneficial.
-   A reference similar to this may need to include a build-specific file name based upon a hash or something along those lines for HTTP cache purposes.
-   Also consider enabling source maps to assist with debugging and testing.

  

-   **Writing and Formatting JavaScript**
-   The use of whitespace should follow long-standing English writing conventions, with blank lines between ideas and groups of code such as objects, functions, and new lines for new statements.
-   Formatting the language statements and patterns should follow these basics:

-   **Open braces** are preceded by a single space.
-   **Open braces** should appear on the same line as their preceding argument.
-   **Close braces** should appear at the same indentation as the statement preceding the opening brace
-   There should be no space characters between **parentheses** and their contents.
-   Use **semicolons** and do not rely on automatic semicolon insertion.
-   Each **comma** and **colon** (and semi-colons that don't end a line) should be followed by a single space.
-   **Binary** and **ternary operators** should have a single space on each side.
-   **Quoted values** should be in 'single quotes' so that double quotes may easily exist inside them.
-   **Comment JavaScript** code thoroughly and consider using a pattern such as those described by [JSDocs](http://usejsdoc.org/) so that documentation may be generated automatically.
-   Conditional statements go on a new line followed by the opening brace.
-   Else/else go on the same line as the brace.
-   Use type strict checks with === as opposed to == whenever possible.

-   ```
-   for (var i = 0, len = arr.length; i < len; i++) {
-   var example = 1;
-   if (example === i) {
-   // we are looping
-   } else {
-   // this will never happen
-   }
-   }
-   ```

  

-   Use single quotes for strings except to avoid escaping
-   ```

-   console.log('hello there') // ✓ ok
-   console.log("hello there") // ✗ avoid
-   console.log(`hello there`) // ✗ avoid
-   $("<div class='box'>")  // ✓ ok

-   ```
-   For multi-line statements, use curly braces
-   Infix operators must be spaced
-   Multiple blank lines should be avoided and are not allowed
-   Declare browser globals with a comment such as /*global*/ for readability

  

-   **Best Practices**
-   Avoid user-agent sniffing and rely on [feature detection](https://isobar-us.github.io/code-standards/#javascript_feature-detection) instead. Browser detection is dangerous and error-prone.

-   Avoid using document.write.
-   Only run scripts on a page that are needed for that page.
-   Don't repeat yourself (i.e. keep your code [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself))
-   Do not modify JavaScript core objects .prototype unless you really know what you're doing.
-   Use method names that make sense, such as init() or setup() for code that starts things off. Be consistent on your project.

  

-   **Variable Scope**
-   Minimize the use of global or window level variables and name-spaces. Pollution of the global name-space is error prone and a bad practice.
-   If referencing a window or global level variable that isn't obvious, please comment as such or explicitly state it.
-   ```
-   var window.thing = {};
-   ```

  

-   **Variable Names and Types**
-   Always use meaningful variable names that can be read as words, not as abbreviations only you understand.

-   Variable names should be camelCase.
-   Objects, classes, and name-spaces should be TitleCase.
-   Boolean values should be prefixed with is if at all possible.
-   Cached jQuery objects can be prefixed with $.
-   Use shorthand versions of empty Arrays and Objects.

-   ```
-   // some examples
-   var exampleValue = 'my example variable value';
-   var numberOfTimes = 3;
-   // booleansvar isThisWorking = true;
-   var isNotWorking = 0;
-   // cache a selector
-   var $body = $('body');
-   // short hand objects and arrays
-   var newObject = {};
-   var newArray = [];
-   ```

  

-   **Settings, Constants**
-   Put settings together in obvious places such as an Object literal space inside your module. Make settings that are possibly to be considered "constants" to be obvious -- some developers like to use ALLCAPS.

  

-   **Feature Detection**
-   Always test for the existence of a browser API, function, or object property before you use it, and make sure the user experience is still functional (to the extent possible) if it's not found. We rely on JavaScript-based feature detection rather than server-side device detection because it's more robust, easily maintained, and future-proof. The go-to library for feature detection is of course [Modernizr](http://modernizr.com/).

  

-   **Limit Events — Use Event Delegation**
-   It is always preferable to use fewer events being bound to objects on a page as possible. Too many events bound on a page can mean memory leaks or just an accumulation of handlers bound to DOM elements which becomes less and less efficient over time. Additionally, event delegation has the added benefit of persisting events over dynamic page updates when items are added or removed from the DOM.
-   With jQuery this is easy, simply use the on method with a selector:
-   ```
-   $('body').on('click', 'a.scroller', function(){
-   // this only runs if the a.scroller is matched
-   });

  

  

Responsive Design Best Practices

-   **Media Queries and CSS Breakpoints**

  

-   Media queries consist of a media type and at least one expression of a media feature (such as height, width and orientation) that describe the conditions under which a set of CSS rules apply.
-     
    
-   Don’t specify vendor- or device-specific widths. Let the content and the design dictate the breakpoints.

  

-   IE8 and below do not support Media Queries. [Respond.js](https://github.com/scottjehl/Respond) (and similar JavaScript libraries) can be used to enable support for Media Queries in these older browsers (if needed).

-   You are better off forcing older browsers to experience the site through a desktop experience (optionally tailored specifically for these older browsers).

  

-   **Mobile First**

  

-   The "Mobile First" techniques consider the lowest common denominator first, which is likely to be your mobile devices due to bandwidth limitations, loading times (not just screen size!), and even CPU speed of the devices.

  

-   Start small, and work upwards. Use min-width, **not** max-width breakpoint definitions.
-   Begin with global content styles that apply across all breakpoints.
-   Examine site features for mobile-specific JavaScript events (e.g. touch, pointer, vs. mouse) and interactions (e.g. swipe).

  

-   ```
-   /* GENERAL STYLES */.example {...}
-   /* SECTION SPECIFIC STYLES - aimed at the smallest devices*/.hero {...}
-   @media(min-width: 600px) {
-   .hero {
-   /* just the new stuff here, no need to be repetitive... */
-   } }
-   @media(min-width: 800px) {
-   .hero {
-   /* just the new stuff here, no need to be repetitive... */
-   } }
-   @media(min-width: 1400px) {
-   .hero {
-   /* might need larger font sizes at largest screen sizes */
-   } }
-   ```
-   Note: the breakpoints specified above are **not** intended to be recommended breakpoints, but rather just illustrative of this general concept.

  

-   **Performance**

  

-   People expect page load time to be as fast if not faster on their mobile phones in comparison to a desktop experience.

  

-   Advanced CSS3 techniques are easy to implement, but when you start combining them, rendering and scrolling performance can be affected. Be careful of images, make sure you are serving a mobile optimized image.

  

-   Try to keep your Web site's foot print as small as possible.
-   Consider every HTTP request.
-   Start with global styles that apply across all breakpoints.
-   Concatenate, gzip and minified your production CSS/JS where possible as this will lower page load size and time
-   Load the least amount of JavaScript that is needed.
-   Wherever possible include script files at the end of your HTML document just before the </body> tag.

  

  

-   **Responsive Images**

  

-   Currently there is little to no native support for responsive images.

  

-   **Always** optimize your images using a tool such as Adobe Photoshop to assure you have the ideal image size and right amount of lossy compression.

  

-   **Vector Graphics (SVG)**

  

-   When working with an audience on unknown screen sizes and resolutions, as is the pretense in web development, having graphics that can scale without degrading is a very appealing prospect.
-     
    
-   Web fonts

-   Pros: this option allows for easy control of vector color, size and usage
-   Cons: all of the vectors single color and must be grouped others in one file.

  

-   SVG

-   Pros: vectors can be manipulated by CSS and/or JavaScript and allows for complex filters, animations and transitions.
-   Cons: SVG is only supported by IE9+

  

-   **Responsive Data Tables**

  

-   Displaying data tables in a responsive way on Mobile sites is a challenge. There are only so many good ways to address this. Brad Frost provides excellent guidance on  [responsive data tables](https://bradfrost.github.io/this-is-responsive/resources.html#tables).
-     
    

-   Simply make a wrapper around the table and scroll horizontally.
-   Have CSS rules which collapse the tables.
-   Sometimes JavaScript might be used to hide/show certain less critical columns, however this does add overhead.

  

  

-     
    

Advanced Topics

Design Systems primer: [https://uxdesign.cc/everything-you-need-to-know-about-design-systems-54b109851969](https://uxdesign.cc/everything-you-need-to-know-about-design-systems-54b109851969)

Deploying to AWS with Docker: [https://aws.amazon.com/getting-started/tutorials/deploy-docker-containers/](https://aws.amazon.com/getting-started/tutorials/deploy-docker-containers/)

Prototyping with React: [https://dev.to/pineapplecontent/prototyping-best-practices-using-react-for-front-end-developers-4l55](https://dev.to/pineapplecontent/prototyping-best-practices-using-react-for-front-end-developers-4l55)

  

  

More Resources

Github best practices: [https://dev.to/datreeio/top-10-github-best-practices-3kl2](https://dev.to/datreeio/top-10-github-best-practices-3kl2)

NPM best practices: [https://www.codementor.io/@mattgoldspink/nodejs-best-practices-du1086jja](https://www.codementor.io/@mattgoldspink/nodejs-best-practices-du1086jja)

React best practices: [http://www.jancarloviray.com/blog/react-best-practices-2020/](http://www.jancarloviray.com/blog/react-best-practices-2020/)

CI/CD best practices: [https://www.javacodegeeks.com/2020/03/ci-cd-pipeline-demystifying-the-complexities.html](https://www.javacodegeeks.com/2020/03/ci-cd-pipeline-demystifying-the-complexities.html)

AWS best practices: [https://www.parkmycloud.com/blog/aws-best-practices/](https://www.parkmycloud.com/blog/aws-best-practices/)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwODYwNDk4MDgsMTc5NDg3MTA2MCwtOD
I3OTczMDY0LDE1NDkwNzg3MDIsNDI5MjAyNTE2XX0=
-->