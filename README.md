# Serverside-Rendering

### Server-Side rendering is the most common method for displaying information onto the screen. It works by converting HTML files in the server into usable information for the browser.

##### Whenever you visit a website, your browser makes a request to the server that contains the contents of the website. The speed of that request depends on a multiple factors such as your internet speed, the location of the server, how many users are trying to access the site, etc.

##### Once the request is done processing, your browser gets back the fully rendered HTML and displays it on the screen. If you then decide to visit a different page on the website, your browser will once again make another request for the new information. This will occur each and every time you visit a page that your browser does not have a cached version of.

##### The most common use case for server-side rendering is to handle the initial render when a user (or search engine crawler) first requests our app. When the server receives the request, it renders the required components into an HTML string, and then sends it as a response to the client. From that point on, the client takes over rendering duties.

### Client-Side Rendering

##### Client-side rendering is about rendering the content in the browser using JavaScript. So instead of getting all of the content from the HTML document itself, you are getting an HTML document with a JavaScript file that will render the rest of the site using the browser.

##### Client-side rendering is when the client-side environment is used to run scripting. The source code is transferred from the web server to the user’s device and then run, typically in a browser.


#### Pros and cons of serverside rendering vs clientside

#### Server-Side pros:
1-Rich site interactions
2-Fast website rendering after the initial load.
3-Great for web applications.
4-Robust selection of JavaScript libraries.

#### Server-Side cons:
1-Low SEO if not implemented correctly.
2-Initial load might require more time.
3-In most cases, requires an external library.


#### Client-Side pros:

1-Faster navigation
2-Server performance
3-Architecture
4-Improved development speed
5-Testability

#### Client-Side cons:
1-Slower Initial Load
2-Unpredictable Performance
3-Compatibility with older browsers
4-Search Engine Optimization
5-Maintainability


## Problems templating languages solve

#### Templating Languages

This allows for reuse of the static elements of a web page, while allowing the dynamic elements to be defined based on the parameters of the web request. Web templates are also used in the creation of static content, providing a basic structure and appearance characteristic for web content.

##### Pros:

- Encourages good code organization (data generation is separate from presentation code)
- Output generation is more expressive (template syntax doesn't require a sea of string concatenation)
- Better productivity (common problems such as output encoding, iterating, conditionals, etc. have been handled)
- Generally requires less code overall (jade in particular has a very terse syntax)

## Examples of functionality that templating languages provide

Functions are called by using their name followed by the required parameters separated by spaces.

### Functions:

#### *Example 1:*  Adding Numbers

> {{ add 1 2 }}

> => 3

#### *Example 2:*  Comparing Numbers
> {{ lt 1 2 }}

> => true (i.e., since 1 is less than 2)

### Logic

#### *Example 1:*   Using Context

>{{ range array }}

>    {{ . }}

>{{ end }}

### Conditionals

`if`, `else`, `with`, `or`, and `and` provide the framework for handling conditional logic. Like `range`, each statement is closed with an `{{end}}`.


#### *Example 1:* `if`

>{{ if isset .Params "title" }} ``` <h4> {{ index .Params "title" }}</h4>``` {{ end }}


#### *Example 2:* `if` … `else`

>{{ if isset .Params "alt" }}

>    {{ index .Params "alt" }}

>{{else}}

>    {{ index .Params "caption" }}

> {{ end }}

#### *Example 3:* `and` & `or`
> {{ if and (or (isset .Params "title") (isset .Params "caption")) (isset .Params "attr")}}

