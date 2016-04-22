#### General Questions:

### What did you learn yesterday/this week?
More about building single page applications with AngularJS

### What excites or interests you about coding?
All the kinds of applications that you can build

### What is a recent technical challenge you experienced and how did you solve it?

Recently it's been about learning more about APIs and intergradting them into my applications. I solved it by calling console.log to see what the data I was getting back from the API call and then pulled out the data I needed from that JSON file.

### What UI, Security, Performance, SEO, Maintainability or Technology considerations do you make while building a web application or site?

For the UI it depends on what the the application is for and what kind of users will be using this application. Is it for more general use, so does it need a more simple UI or is it for more techinical people that need more information then a UI.

Security, again, it depends on the situation. Generally, it's a good idea to have some kind of security with something that is pulling user data or sites that are going out to external sites for information.

Maintainability It's a good idea to document things, have good clean code that people can understand. Have some source control so you have a history of what changes where made and when.

Technology Use what works best for the situation at hand. Also make sure what you are using is going to be supported later one when you want to update things.
  
### Talk about your preferred development environment.

MacOX
Brackets / Sublime
chrome / firefox
git

### Which version control systems are you familiar with?
git

### Can you describe your workflow when you create a web page?
- Create a prototype with just rough elements.
- Set up a basic structure with just html and rough links
- Break down the code into smaller bits and build up from there.
- Add the interaction and User intergration

### If you have 5 different stylesheets, how would you best integrate them into the site?
- Try to combine them into one file if possible.
- If it's using something like Bootstrap, try to create the new styles outside of Bootstraps

### Can you describe the difference between progressive enhancement and graceful degradation?

- Graceful degradation is the practice of building your web functionality so that it provides a certain level of user experience in more modern browsers, but it will also degrade gracefully to a lower level of user in experience in older browsers. This lower level is not as nice to use for your site visitors, but it does still provide them with the basic functionality that they came to your site to use; things do not break for them.

- Progressive enhancement is similar, but it does things the other way round. You start by establishing a basic level of user experience that all browsers will be able to provide when rendering your web site, but you also build in more advanced functionality that will automatically be available to browsers that can use it.

- In other words, graceful degradation starts from the status quo of complexity and tries to fix for the lesser experience whereas progressive enhancement starts from a very basic, working example and allows for constant extension for future environments. Degrading gracefully means looking back whereas enhancing progressively means looking forward whilst keeping your feet on firm ground.


### How would you optimize a website's assets/resources?
- File concatention and minification (using browserify for example)
- Minification of images
- Try to avoid too many calles to outside databases and queries.

### How many resources will a browser download from a given domain at a time?
- Chrome it is 6, Firefox 6, IE11 is 8
  * What are the exceptions?
- The limits are per domain, so you could do a wildcard DNS.

### Name 3 ways to decrease page load (perceived or actual load time).
- Minimize images
- Minimize and combine Javascript
- Minimize CSS automatically or by removing unused styles.

### If you jumped on a project and they used tabs and you used spaces, what would you do?
- Suggest the project utilize something like EditorConfig
- Keep with what they are doing and bring it up in a meeting later.

### Describe how you would create a simple slideshow page.
- Wrap up the images in a div tag
- Use CSS to hide the images that do not need to be displayed.
- Use Javascript to create a navigvation (using an array possibly)

     slideshow { 
            margin: 50px auto; 
            position: relative; 
            width: 240px; 
            height: 240px; 
            padding: 10px; 
            box-shadow: 0 0 20px rgba(0,0,0,0.4); 
        }

    slideshow > div { 
        position: absolute; 
        top: 10px; 
        left: 10px; 
        right: 10px; 
      bottom: 10px; 
    }

    $("#slideshow > div:gt(0)").hide();

      setInterval(function() { 
      $('#slideshow > div:first')
        .fadeOut(1000)
        .next()
        .fadeIn(1000)
        .end()
        .appendTo('#slideshow');
     },  3000);

### If you could master one technology this year, what would it be?
Angular JS

### Explain the importance of standards and standards bodies.
Standards describe how a thing does and should work. It is extremely important especially in software, because the thing can be used by many people for different perposes. For example, there are several engines for JavaScript including V8, JavaScriptCore, Rhino, etc, and if there is no standard for the language, developers and users cannot feel ensured when doing something with it.

### What is Flash of Unstyled Content? How do you avoid FOUC?
- It is caused when content is loaded before styles are applied to the content. It happens when style tags are placed after other content, or applied asynchronously, for example, by scripts.

- To avoid FOUC, the styles should be placed in order that they can be loaded and applied in the same rendering process as HTML elements do. The easiest way is to place them in the head, and avoid applying styles by scripts at the first load.

### Explain what ARIA and screenreaders are, and how to make a website accessible.
They are for accessibility. To make a website accessible, we should try to follow the usage of HTML elements, for example, h1 for headers and section for sections. Also it's good to take care of using visual contents, such as not forgetting to add an alt attribute to img tags.

### Explain some of the pros and cons for CSS animations versus JavaScript animations.
- **CSS**
- Pro Use GPU so less CPU effecient, they do not consume Javascript event loops
- Cons Hard to handle as the CSS doesn't contain logic and not supported in older browsers.

- **Javascript**
- Pro Easy to handle as they have logic
- Con Use CPU 

### What does CORS stand for and what issue does it address?
CORS stands for cross-origin resource sharing. There could be situation where some resources should be allowed from sources having different origin. CORS is a standard to enable cross-site HTTP requests for:

- AJAX API call
- Web Fonts
- WebGL textures
- Image/video frames drawn to a canvas using drawImage
- Stylesheets
- Scripts

#### HTML Questions:

### What does a `doctype` do?
The doctype declaration should be the very first thing in an HTML document, before the tag. The doctype declaration is not an HTML tag; it is an instruction to the web browser about what version of the markup language the page is written in. The doctype declaration refers to a Document Type Definition

HTML 5 <!DOCTYPE html>
XML 1.0 <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">

### What's the difference between standards mode and quirks mode?
There are now three modes used by the layout engines in web browsers: quirks mode, almost standards mode, and full standards mode. In quirks mode, layout emulates nonstandard behavior in Navigator 4 and Internet Explorer 5. This is essential in order to support websites that were built before the widespread adoption of web standards. In full standards mode, the behavior is (hopefully) the behavior described by the HTML and CSS specifications. In almost standards mode, there are only a very small number of quirks implemented.

Biggest one being the CSS box model.

### What's the difference between HTML and XHTML?
- Short answer: xHTML is XML, HTML is not.
- xHTML is the XML version of HTML. 
- To understand this answer you have to know what XML is : it's a markup language designed to format data in a way that's easy to understand for a human, and also easy to parse for a machine.
- XML is also a meta-language. This means that a lot of languages are based on XML, with rules and grammar defined to make a language with specific purpose from XML. Some well-known  examples are OpenMath, MML, XPath, XQuery, ...
- Now at the beginning of the web, the markup language that was used for web pages was HTML. It looks a lot like XML but it's not an XML language because it does not respect the XML standard.
- Later, xHTML was invented with respect to the XML standard. It is more strict than html because you have to respect all the xml rules (Closing tag for each opening tag, attributes have to have a value etc.)

### Are there any problems with serving pages as `application/xhtml+xml`?
- The XHTML page must be well formed.If you forgot to closed a element and the browser will not to closed it and cause error.
- For "application/xhtml+xml", some old browsers no supports.

### How do you serve a page with content in multiple languages?
- You must have translated/localized pages on the server for each language you intend to support.
- Your server must recognize the browser’s language request.
- You must carefully name the files for the localized pages, so the server has a systematic way of locating them.
- You need a method for serving a generic page when you don’t have the requested language.

### What kind of things must you be wary of when design or developing for multilingual sites?
Another problem with many solutions: setting the default language, using Unicode encoding, using the ‘lang’ attribute, being aware of standard font sizes and text direction, and language word length (may affect layout).

### What are `data-` attributes good for?
The HTML5 data- attribute is a new addition that assigns custom data to an element. It was built to store sensitive or private data that is exclusive to a page or application, for which there are no other matching attributes or elements.

### Consider HTML5 as an open web platform. What are the building blocks of HTML5?
The main building blocks are centred on HTML 5, CSS3, Javascript and SVG. Where HTML is a language to define the mark-up of a document (titles, headers, body, footer, tables, input forms etc.), CSS is a language to define style (formatting, colours, shades and the like). Javascript is a programming/scripting language and SVG is a language for creating 2D scalable vector graphics and images.

### Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
They are all storage on the client side. cookies is small piece of key-value pair (A key-value pair is a set of two linked data items: a key, which is a unique identifier for some item of data, and the value, which is either the data that is identified or a pointer to the location of that data. Key-value pairs are frequently used in lookup tables, hash tables and configuration files.) with a expire time. sessionStorage is on persistent and scope only to current windows. localStorage is persisitent and socop only to domain, by key-value pair or SQL database (Web SQL)

### Describe the difference between `<script>`, `<script async>` and `<script defer>`
*Normal execution (script)* 
- This is the default behavior of the script element. Parsing of the HTML code pauses while the script is executing. For slow servers and heavy scripts this means that displaying the webpage will be delayed.

*Deferred execution (script async)*
- Simply put: delaying script execution until the HTML parser has finished. A positive effect of this attribute is that the DOM will be available for your script. However, since not every browser supports defer yet, don’t rely on it!

*Asynchronous execution (script async)*
- Don’t care when the script will be available? Asynchronous is the best of both worlds: HTML parsing may continue and the script will be executed as soon as it’s ready.

To explain is a lot easier, defer is the equivalent of jQuery.ready() - it means your script is guaranteed that the DOM is ready and all HTML has been parsed. Async means the file can potential load before the DOM is even parsed, which means you more than likely will not have access to the DOM.

### Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?

*Here is what happens when a browser loads a page*
- Fetch the HTML page (e.g. index.html)
- Begin parsing the HTML
- The parser encounters a script tag referencing an external script file.
- The browser requests the script file. Meanwhile, the parser blocks and stops parsing the other HTML on your page.
- After some time the script is downloaded and subsequently executed.
- The parser continues parsing the rest of the HTML document.

Any script can insert its own HTML via document.write() or other DOM manipulations. This implies that the parser has to wait until the script has been downloaded and executed before it can safely parse the rest of the document. After all, the script could have inserted its own HTML in the document.

Because your browser does not know my-script.js isn't going to modify the document until it has been downloaded & executed, the parser stops parsing.

*Antiquated recommendation*
The old approach to solve this problem was to put script tags at the bottom of your body, because this ensures the parser isn't blocked until the very end.

This approach has its own problem: the browser cannot start downloading the scripts until the entire document is parsed. For larger websites with large scripts and stylesheets, being able to download the script as soon as possible is very important for performance. If your website doesn't load within 2 seconds, people will go to another website.

In an optimal solution, the browser would start downloading your scripts as soon as possible, while at the same time parsing the rest of your document.

*The modern approach*
Today, browsers support the async and defer attributes on scripts. These attributes tell the browser it's safe to continue parsing while the scripts are being downloaded.

*async*

<script type="text/javascript" src="path/to/script1.js" async></script>
<script type="text/javascript" src="path/to/script2.js" async></script>

Scripts with the async attribute are executed asynchronously. This means the script is executed as soon as it's downloaded, without blocking the browser in the meantime.

This implies that it's possible script 2 is downloaded and executed before script 1.

*defer*
<script type="text/javascript" src="path/to/script1.js" defer></script>
<script type="text/javascript" src="path/to/script2.js" defer></script>

Scripts with the defer attribute are executed in order (i.e. first script 1, then script 2). This also does not block the browser.

Unlike async scripts, defer scripts are only executed after the entire document has been loaded.

### What is progressive rendering?
Progressive rendering is the name given to techniques used to render content for display as quickly as possible.

It used to be much more prevalent in the days before broadband internet but it's still useful in modern development as mobile data connections are becoming increasingly popular (and unreliable!)

*Examples of such techniques*

- Lazy loading of images where (typically) some javascript will load an image when it comes into the browsers viewport instead of loading all images at page load.
- Prioritizing visible content (or above the fold rendering) where you include only the minimum css/content/scripts necessary for the amount of page that would be rendered in the users browser first to display as quickly as possible, you can then use deferred javascript (domready/load) to load in other resources and content.

### Have you used different HTML templating languages before?
Only Bourbon and Neat


#### CSS Questions:

### What is the difference between classes and ID's in CSS?
Classes are the general term while ID's are unique. You can use classes over and over, but you can only use ID's once. Best example would be to say that in a class room of students, the students would be the Class, while Joe Smith would be the ID of that student.


### What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
-*Normalize.css preserves useful defaults rather than "unstyling" everything* For example, elements like sup or sub "just work" after including normalize.css (and are actually made more robust) whereas they are visually indistinguishable from normal text after including reset.css. So, normalize.css does not impose a visual starting point (homogeny) upon you. This may not be to everyone's taste. The best thing to do is experiment with both and see which gels with your preferences.

-*Normalize.css corrects some common bugs that are out of scope for reset.css* It has a wider scope than reset.css, and also provides bug fixes for common problems like: display settings for HTML5 elements, the lack of font inheritance by form elements, correcting font-size rendering for pre, SVG overflow in IE9, and the button styling bug in iOS.

-*Normalize.css doesn't clutter your dev tools. A common irritation when using reset.css* is the large inheritance chain that is displayed in browser CSS debugging tools. This is not such an issue with normalize.css because of the targeted stylings.

-*Normalize.css is more modular* The project is broken down into relatively independent sections, making it easy for you to potentially remove sections (like the form normalizations) if you know they will never be needed by your website.

-*Normalize.css has better documentation* The normalize.css code is documented inline as well as more comprehensively in the GitHub Wiki. This means you can find out what each line of code is doing, why it was included, what the differences are between browsers, and more easily run your own tests. The project aims to help educate people on how browsers render elements by default, and make it easier for them to be involved in submitting improvements.

### Describe Floats and how they work.
Float is a CSS positioning property. To understand its purpose and origin, we can look to print design. In a print layout, images may be set into the page such that text wraps around them as needed. This is commonly and appropriately called "text wrap".

In page layout programs, the boxes that hold the text can be told to honor the text wrap, or to ignore it. Ignoring the text wrap will allow the words to flow right over the image like it wasn't even there. This is the difference between that image being part of the flow of the page (or not). Web design is very similar.

In web design, page elements with the CSS float property applied to them are just like the images in the print layout where the text flows around them. Floated elements remain a part of the flow of the web page. This is distinctly different than page elements that use absolute positioning. Absolutely positioned page elements are removed from the flow of the webpage, like when the text box in the print layout was told to ignore the page wrap. Absolutely positioned page elements will not affect the position of other elements and other elements will not affect them, whether they touch each other or not.

    #sidebar {
      float: right;			
    }
       
### Describe z-index and how stacking context is formed.
The z-index property in CSS controls the vertical stacking order of elements that overlap. As in, which one appears as if it is physically closer to you. z-index only effects elements that have a position value other than static (the default).

Elements can overlap for a variety of reasons, for instance relative positioning has nudged it over something else. Negative margin has pulled the element over another. Absolutely positioned elements overlap each other. All sorts of reasons.

Without any z-index value, elements stack in the order that they appear in the DOM (the lowest one down at the same hierarchy level appears on top). Elements with non-static positioning will always appear on top of elements with default static positioning.

Also note that nesting plays a big role. If an element B sits on top of element A, a child element of element A can never be higher than element B.


#### Describe BFC(Block Formatting Context) and how it works.
A block formatting context is a part of a visual CSS rendering of a Web page. It is the region in which the layout of block boxes occurs and in which floats interact with each other.

A block formatting context is created by one of the following:

-The root element or something that contains it
-Floats (elements where float is not none)
-Absolutely positioned elements (elements where position is absolute or fixed)
-Inline-blocks (elements with display: inline-block)
-Table cells (elements with display: table-cell, which is the default for HTML table cells)
-Table captions (elements with display: table-caption, which is the default for HTML table captions)
-Elements where overflow has a value other than visible
-Flex boxes (elements with display: flex or inline-flex)

A block formatting context is a box that satisfies at least one of the following:
-The value of "float" is not "none",
-The used value of "overflow" is not "visible",
-The value of "display" is "table-cell", "table-caption", or "inline-block",
-The value of "position" is neither "static" nor "relative".


### What are the various clearing techniques and which is appropriate for what context?
A clearfix is a way for an element to automatically clear its child elements, so that you don't need to add additional markup. It's generally used in float layouts where elements are floated to be stacked horizontally.

- Empty Div Method
    <div style="clear:both;"></div>

- Overflow Method
    Setting auto or hidden overflow property on parent will expand it to contain the floats.

- The Psuedo Method: uses the parent's :after to add the clear: both property
    
    .clearfix:after { 
    content: "."; 
    visibility: hidden; 
    display: block; 
    height: 0; 
    clear: both;
    }

### Explain CSS sprites, and how you would implement them on a page or site.
A CSS sprite is a big image containing several background images at once. It’s a collection of images combined in one big image. You choose the background image you want to show by playing with the dimensions of the element (which acts like a viewport) and the background position.

-Bandwidth: you just have 1 HTTP request for one image, and the combined image is often lighter than separate images combined
-Rendering: as soon as the sprite is called and displayed once (and even cached), you can re-use it with other elements. Works well with the :hover pseudo-state. There’s no blinking.
-Maintenance: it’s easier in Photoshop or Sketch to export a single asset with everything

Say you had three flags in a row, your CSS would look like this:

    .flags-canada, .flags-mexico, .flags-usa {
      background-image: url('../images/flags.png');
      background-repeat: no-repeat;
    }

    .flags-canada {
      height: 128px;
      background-position: -5px -5px;
    }

    .flags-usa {
      height: 135px;
      background-position: -5px -143px;
    }

    .flags-mexico {
      height: 147px;
      background-position: -5px -288px;
  


### What are your favourite image replacement techniques and which do you use when?
[Nine Techniques for CSS Image Replacement](https://css-tricks.com/css-image-replacement/)

### What are your favourite image replacement techniques and which do you use when?
-Using cross-browser CSS coding. 
The internet explorer is a hard and using this on IE is very hard. 

-Making responsive websites.
But this means having a menu button instead of a bar in many places that we don't want, it can be a problematch.

-Checking with caniuse.com
[caniuse.com](http://caniuse.com/)

### How do you serve your pages for feature-constrained browsers?

The browser market will catch up and you won’t have to update anything because the hacks you implemented won’t be needed, and won’t even be actually called. Plus: it’s less frustrating. You can actually design stuff the way you want, make it both look better and with cleaner code. 

  * What techniques/processes do you use?

### What are the different ways to visually hide content (and make it available only for screen readers)?
**visibility: hidden; and/or display:none;**
These styles will hide text from all users. The text is removed from the visual flow of the page and is ignored by screen readers. Do not use this CSS if you want the content to be read by a screen reader. But DO use it for content you don't want read by screen readers.

**width:0px, height:0px or other 0 pixel sizing techniques**
As above, because an element with no height or width is removed from the flow of the page, most screen readers will ignore this content. HTML width and height may give the same result. Do not size content to 0 pixels if you want the content to be read by a screen reader. Content styled with font-size:0px or line-height:0 may work, though the elements would still take horizontal space on the screen. All of these techniques may result in search engine penalties as they may interpreted to be malicious.

**text-indent: -10000px;**
This approach moves the content to the left 10000 pixels - thus off the visible screen. The actual value matters little, so long as it is positioned off-screen. Screen readers will still read text with this style. However, if a link or form element is given this style, it may result in a focus indicator (the dotted lines or 'marching ants' that surround a focused link) that extends from where the element should be located in the page to the place it is actually located (way to the left). This is not very pretty. This approach also causes issues in right-to-left languages. As such, this approach may be a viable option if the element does not contain navigable elements, though better techniques are available.

### Have you ever used a grid system, and if so, what do you prefer?
I have only ever used the Bootstraps grid system.

So for a grid system, you’d have things like .col-3 and .col-9 for a sidebar and a “main”, in a 12 columns layout. First, the styling is in the HTML. Second, what if you want to put that sidebar on the right and not the left? Well you’d have to modify your HTML structure, instead of changing 2 words in your CSS.

* Have you used or implemented media queries or mobile specific layouts/CSS?

* Are you familiar with styling SVG?

* How do you optimize your webpages for print?

* What are some of the "gotchas" for writing efficient CSS?

* What are the advantages/disadvantages of using CSS preprocessors?
  * Describe what you like and dislike about the CSS preprocessors you have used.

* How would you implement a web design comp that uses non-standard fonts?

* Explain how a browser determines what elements match a CSS selector.

* Describe pseudo-elements and discuss what they are used for. 

* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in 
different box models.

* What does ```* { box-sizing: border-box; }``` do? What are its advantages?

* List as many values for the display property that you can remember.

* What's the difference between inline and inline-block?

* What's the difference between a relative, fixed, absolute and statically positioned element?

* The 'C' in CSS stands for Cascading.  How is priority determined in assigning styles (a few examples)?  How can you use this system to your advantage?

* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?

* Have you played around with the new CSS Flexbox or Grid specs?

* How is responsive design different from adaptive design?

* Have you ever worked with retina graphics? If so, when and what techniques did you use?

* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?

#### JS Questions:

### Explain event delegation
Event delegation allows us to attach a single event listener, to a parent element, that will fire for all descendants matching a selector, whether those descendants exist now or are added in the future.

### Explain how `this` works in JavaScript
- By default, this refers to the global object.
- When a function is called as a property on a parent object, this refers to the parent object inside that function.
- When a function is called with the new operator, this refers to the newly created object inside that function.
- When a function is called using call or apply, this refers to the first argument passed to call or apply. If the first argument is null or not an object, this refers to the global object.

### Explain how prototypal inheritance works
In a nutshell, prototypal inheritance is when an object inherits from another object. This differs from classical inheritance, in which a class inherits from another class.

In a classical language, classes typically define the structure of objects, but in a prototypal language, the objects themselves define their structure, and this structure can be inherited and modified by other objects at runtime.

Prototypal inheritance first appeared in Self and has since appeared in many other languages, but these days most people think of JavaScript when they think of prototypal inheritance.

### What do you think of AMD vs CommonJS?
Basically CommonJS specifies that you need to have a the require() function to fetch dependencies, the exports variable to export module contents and some module identifier (that describes the location of the module in question in relation to this module) that is used to require the dependencies(source). CommonJS has various implementations, for example Node.js that you mentioned.

CommonJS was not particularly designed with browsers in mind so, it doesn't fit to the browser environment very well (I really have no source for this, it just says so everywhere, for example the RequireJS site.). Apparently this has something to do with asynchronous loading etc.

On the contrary, RequireJS implements AMD, which is designed to suit the browser environment(source). Apparently AMD started as an offspin of CommonJS Transport format and evolved into its own module definition API. Hence the similiarities between the two. The new thing in AMD is the define() -function that allows the module to declare its dependencies before being loaded.

So CommonJS and AMD are JavaScript module definition APIs that have different implementations, but both come from the same origins.

- *AMD* is more suited for the browser, because it supports asynchronous loading of module dependencies.
- *RequireJS* is an implementation of AMD, while at the same time trying to keep the spirit of CommonJS (mainly in the module identifiers).

### Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
IIFE stands for Immediately Invoked Function Expressions

An IIFE is an anonymous function that is created and then immediately invoked. It’s not called from anywhere else (hence why it’s anonymous), but runs just after being created.

So, in this case, foo is not being called.

* What needs to be changed to properly make it an IIFE?

```javascript
function foo(){
}();
```
  
  
### What's the difference between a variable that is: `null`, `undefined` or undeclared?
*undeclared* A variable is undeclared when it does not use the var keyword. 
It gets created on the global object (that is, the window), thus it operates in a different space as the declared variables.  

*undefined* Something is undefined when it hasn’t been defined yet. If you call a variable or function without having actually created it yet the parser will give you an not defined error.

*null* null is a variable that is defined to have a null value.

### How would you go about checking for any of these states?
For Undeclared:
Use strict mode

For Undefined:
```javascript
if (typeof(variable) !== "undefined") {
  console.log('variable is not undefined');
} else {
  console.log('variable is undefined');
}
```
For Null
```javascript
if( variable === null ) {
  console.log('variable is null');
} else {
  console.log('variable is not null');
}
```

### How do you organize your code? (module pattern, classical inheritance?)




### What is closure?
A closure is a way of keeping access to variables in a function after that function has returned.

- A closure is the local variables for a function — kept alive after the function has returned
- A closure is a stack-frame which is not deallocated when the function returns (as if a 'stack-frame' were malloc'ed instead of being on the stack!).

The following code returns a reference to a function:

```javascript
function sayHello2(name) {
    var text = 'Hello ' + name; // Local variable
    var say = function() { console.log(text); }
    return say;
}
var say2 = sayHello2('Bob');
say2(); // logs "Hello Bob"
```

### What's the difference between host objects and native objects?
*Native Objects*
Object in an ECMAScript implementation whose semantics are fully defined by this specification rather than by the host environment.

Examples: Object (constructor), Date, Math, parseInt, eval, string methods like indexOf and replace, array methods

*Host Objects*
Object supplied by the host environment to complete the execution environment of ECMAScript.
NOTE Any object that is not native is a host object.

Examples: window, document, location, history, XMLHttpRequest, setTimeout, getElementsByTagName, querySelectorAll

### What's a anonymous functions?

An anonymous function is a function that was declared without any named identifier to refer to it. As such, an anonymous function is usually not accessible after its initial creation.

    function hello() {
      alert('Hello world');
    }
    hello();

### What's a typical use case for anonymous functions?
*Pros*
- Flexibility. An asynchronous function with a callback paramater could be reached by one of many different code paths and it could be harried to have to write a named function to account for every single possible edge case.
- Speed. It plays heavily in to the hacker mentality. Bolt things on to it until it works.
- Smaller file sizes, even if trivially so, but every bit counts on the web.
- Simpler AST? I would assume that anonymous functions are generated at runtime and so the JIT won't muck about with mapping the name to instructions, but I'm just guessing at this point.
- Quicker dispatching? Not sure about this one either. Guessing again.

*Cons*
- It's hideous and unreadable
- It adds to the confusion when you're nested nuts deep in a swamp of callbacks (which, to be fair, probably means you're writing poorly constructed code to begin with, but it's quite common).
- For someone without a functional background it can be a bizarre concept to grok

### How do you organize your code? (module pattern, classical inheritance?)
**Modular pattern**
Modular pattern imitates the classes in conventional software engineering and it mainly focuses on the public and private access to methods & variables. The module pattern goals are to reduce the use of globally scoped variables, so as to decreasing the chances of conflicting with other code throughout an application.

This is also regarded as the most commonly used design pattern and it is also widely accepted in a number of large projects such as jQuery, Dojo, ExtJS and YUI.

**Advantages**
- Organized and clean approach for developers
- We can encapsulate data.
- More clean code in the global namespace(avoiding conflicts).

**Disadvantages**
- We cannot access private methods
- We can extend Private methods and functions.

**Classical Inheritance**
The classical inheritance in a way is similar to the inheritancein Java or C. Those who have backgrounds in those programming languages must be familiar. So by using classical inheritance, we are recreating the basic programming language’s behavior i.e. using classes and objects, which are instances of those classes.

So a classical pattern is used together with the“prototype”keyword added to the constructor and the newoperator.
- Call a constructor function.
- Have a child’s prototype point to the parent’s prototype.

### Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
**function Person() {}**
Declares a function (but does not execute it).
It will usually have some code between the curly brackets.

**var person = Person()**
Declares a variable (person), invokes a function (Person) and sets the value of person to the return of the function.

**var person = new Person()**
Creates a new instance of an object based on the Person function. So the variable (person) is now an Object, not just a string or a number.

### What's the difference between `.call` and `.apply`?
The difference is that apply lets you invoke the function with arguments as an array; call requires the parameters be listed explicitly. A useful mnemonic is "A for array and C for comma."

The apply() method is identical to call(), except apply() requires an array as the second parameter. The array represents the arguments for the target method.

### Explain `Function.prototype.bind`.
The bind() method creates a new function that, when called, has its this keyword set to the provided value, with a given sequence of arguments preceding any provided when the new function is called.

### When would you use `document.write()`?
The document.write methods outputs a string directly into page.

When document is loading, a script may document.write(text) into the document. The text will be rendered same way as if it were in HTML.

document.write (henceforth DW) does not work in XHTML

### What's the difference between feature detection, feature inference, and using the UA string?

**Feature detection** is to verify if a feature works in a particular browser or not. The feature can be either a CSS property or a Java Script Method.

if (window.XMLHttpRequest) {
    new XMLHttpRequest();
}

**Feature inference** is to assume that a CSS property/ JS method is available in all the browsers, by verifying it in a single browser. The fact is it can or it cannot be available. For ex. the text( ) function is implemented in Chrome , but it is not implemented in Firefox which will give out an error eventually when used. So we have to be careful.

if (document.getElementsByTagName) {
    element = document.getElementById(id);
}

**Checking the UA string** is a software which identifies your operating system, browser and its version. When you a visit a particular webpage, the browser sends a user-agent string to the host, implying that only the content/data related to that particular browser should be displayed.

if (navigator.userAgent.indexOf("MSIE 7") > -1){
    //do something
}

### Explain AJAX in as much detail as possible.
Asynchronous JavaScript and XML, the method of exchanging data with a server, and updating parts of a web page - without reloading the entire page.”

AJAX allows web pages to be updated asynchronously by exchanging small amounts of data with the server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page.

Classic web pages, (which do not use AJAX) must reload the entire page if the content should change.

Examples of applications using AJAX: Google Maps, Gmail, YouTube, and Facebook.

### Explain how JSONP works (and how it's not really AJAX).
**JavaScript Object Notation with padding**
When you make your request to a server that is JSONP enabled, you pass a special parameter that tells the server a little bit about your page. That way, the server is able to nicely wrap up its response in a way that your page can handle.

JSONP, when the server receives the "callback" parameter, it wraps up the result a little differently, returning something like this:
`mycallback({ foo: 'bar' });`

### Have you ever used JavaScript templating?
Yes, but only jQuery

**If so, what libraries have you used?**
-jQuery



### Explain "hoisting".
Hoisting is JavaScript's default behavior of moving declarations to the top.

Any variable declared inside of a block is moved to the top.

In JavaScript, a variable can be declared after it has been used.

In other words; a variable can be used before it has been declared.

     x = 5;

     elem = document.getElementById("demo"); 
     elem.innerHTML = x;

     var x;

result is 5


* Describe event bubbling.

### What's the difference between an "attribute" and a "property"?

JS DOM objects have properties. These properties are kind of like instance variables for the particular element. As such, a property can be different types (boolean, string, etc.). Properties can be accessed using jQuery’s prop method (as seen below) and also by interacting with the object in vanilla JS.

$('#linkID').prop('href');
returns "http://example.com/page2.html"

$('#linkID').prop('name');
returns "linkName"

$('#linkID').prop('id');
returns "linkID"

$('#linkID').prop('className');
returns "link classes"


Attributes are in the HTML itself, rather than in the DOM. They are very similar to properties, but not quite as good. When a property is available it’s recommended that you work with properties rather than attributes.

An attribute is only ever a string, no other type.

$('input').prop('checked')
returns true

$('input').attr('checked');
returns "checked"

* Why is extending built-in JavaScript objects not a good idea?

* Difference between document load event and document ready event?


### What is the difference between `==` and `===`?

- Two strings are strictly equal when they have the same sequence of characters, same length, and same characters in corresponding positions.
- Two numbers are strictly equal when they are numerically equal (have the same number value). NaN is not equal to anything, including NaN. - Positive and negative zeros are equal to one another.
- Two Boolean operands are strictly equal if both are true or both are false.
- Two objects are strictly equal if they refer to the same Object.
- Null and Undefined types are == (but not ===). [I.e. (Null==Undefined) is true but (Null===Undefined) is false]

0 == false is true

0 === false is false, because they are of a different type

1 == "1"    is true, automatic type conversion for value only

1 === "1"    is false, because they are of a different type

null == undefined is true

null === undefined is false

'0' == false is true

'0' === false is false

* Explain the same-origin policy with regards to JavaScript.

### Make this work:
```javascript
duplicate([1,2,3,4,5]);

outputs [1,2,3,4,5,1,2,3,4,5]

Array.prototype.duplicator = function(){
    return this.concat(this);
}
alert([1,2,3,4,5].duplicator());

```

* Why is it called a Ternary expression, what does the word "Ternary" indicate?
* What is `"use strict";`? what are the advantages and disadvantages to using it?

### Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`

```javascript
for (number=1: number<100; i++;)
    if ( number %=== 0 );
      print('buzz');
      } if (number % 15){
          print('fizzBuzz');
        } if (number % 3){
          print('fizz')
          } else {
            print(number);
          }
        }
      }
number(100);
```


* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
* Explain what a single page app is and how to make one SEO-friendly.
* What is the extent of your experience with Promises and/or their polyfills?
* What are the pros and cons of using Promises instead of callbacks?
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
* What tools and techniques do you use debugging JavaScript code?
* What language constructions do you use for iterating over object properties and array items?
* Explain the difference between mutable and immutable objects.
  * What is an example of an immutable object in JavaScript?
  * What are the pros and cons of immutability?
  * How can you achieve immutability in your own code?
* Explain the difference between synchronous and asynchronous functions.
* What is event loop?
  * What is the difference between call stack and task queue?

#### Testing Questions:

* What are some advantages/disadvantages to testing your code?
* What tools would you use to test your code's functionality?
* What is the difference between a unit test and a functional/integration test?
* What is the purpose of a code style linting tool?

#### Performance Questions:

* What tools would you use to find a performance bug in your code?
* What are some ways you may improve your website's scrolling performance?
* Explain the difference between layout, painting and compositing.

#### Network Questions:

* Traditionally, why has it been better to serve site assets from multiple domains?
* Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
* What are the differences between Long-Polling, Websockets and Server-Sent Events?
* Explain the following request and response headers:
  * Diff. between Expires, Date, Age and If-Modified-...
  * Do Not Track
  * Cache-Control
  * Transfer-Encoding
  * ETag
  * X-Frame-Options
* What are HTTP actions? List all HTTP actions that you know, and explain them.

#### Coding Questions:

### Question: What is the value of `foo`?*
```javascript
var foo = 10 + '20';
```
10

### Question: How would you make this work?*
result 7
```javascript
add(2, 5);
add(2)(5);
```
```javascript
var add = function(x) {
    return function(y) { return x + y; };
}
```

### Question: What value is returned from the following statement?*
```javascript
"i'm a lasagna hog".split("").reverse().join("");
```
“goh angasal a m’i”

### Question: What is the value of `window.foo`?*
```javascript
( window.foo || ( window.foo = "bar" ) );
```
bar, if intially window.foo was false, undefined or zero else it will retain its value.

*Question: What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```
Hello World and ReferenceError: bar is not defined

### Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```
foo.length = 2

### Question: What is the value of `foo.x`?*
```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```
undefined

- determines that foo.x refers to a property x of the {n: 1} object
- assigns {n: 2} to foo
- assigns the new value of foo  {n: 2}  to the property x of the {n: 1} object.

*Question: What does the following code print?*
```javascript
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
console.log('three');
```


#### jQuery Questions:

### Explain “chaining”
Chaining in jQuery is when you apply multiple method events one after the other. $().split().join()

### What does .end() do? .end()
- Stops an event that is in queue so the next even can occur
- It can also go back to the parent set.

### What is the effects (or fx) queue? 
Queues are the foundation for all animations in jQuery, they allow a series functions to be executed asynchronously on an element. Methods such as .slideUp(), .slideDown(), .fadeIn(), and .fadeOut() all use .animate(), which leverages queues to build up the series of steps that will transition one or more CSS values throughout the duration of the animation.

### What is the difference between .get(), [], and .eq()?
.get() and .eq() both return a single "element" from a jQuery object array, but they return the single element in different forms.

.eq() returns it as a jQuery object, meaning the DOM element is wrapped in the jQuery wrapper, which means that it accepts jQuery functions.

.get() return a raw DOM element. You may manipulate it by accessing its attributes and invoking its functions as you would on a raw DOM element. But it loses its identity as a jQuery-wrapped object, so a jQuery function like .fadeIn won't work.

### What is the difference between .bind(), .live(), and .delegate()?
.bind() attacheds events to elements that exist or match the selector at the time the call is made. Any elements created afterwards or that match going forward because the class was changed, will not fire the bound event.

.live() works for existing and future matching elements. Before jQuery 1.4 this was limited to the following events: click, dblclick mousedown, mouseup, mousemove, mouseover, mouseout, keydown, keypress, keyup

.delegate() method behaves in a similar fashion to the .live() method, but instead of attaching the selector/event information to the document, you can choose where it is anchored. Just like the .live() method, this technique uses event delegation to work correctly.

In short: .bind() will only apply to the items you currently have selected in your jQuery object. .live() will apply to all current matching elements, as well as any you might add in the future.

### What is the difference between $ and $.fn? Or just what is $.fn. 
$ is a function (specifically, a variable pointing to the jQuery function — an alias). $.fn is a property on that function, which points to the prototype of the internal init function jQuery uses to create instances, as we can see in the jQuery code:

jQuery.fn.init.prototype = jQuery.fn;

$.fn is there so that it's easy to add properties to it. When you create jQuery objects, they have those properties, because of JavaScript's prototypical inheritance. The most common properties to add to it are, of course, functions that do things (jQuery plug-ins).

### Optimize this selector: javascript $(“.foo div#bar:eq(0)”)
$(“.foo div#bar”).eq(0);

#### Fun Questions:

* What's a cool project that you've recently worked on?
* What are some things you like about the developer tools you use?
* Do you have any pet projects? What kind?
* What's your favorite feature of Internet Explorer?
* How do you like your coffee?
