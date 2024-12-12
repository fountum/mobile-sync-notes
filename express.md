- # EXPRESS
	- ### WHAT
		- Web app framework
		- Sites on top of node.js
			- wrapper for node:html
			- anything possible in express.js is possible in node.js
	- ### WHY
		- Easily access DB and other companies' servers
	- ## Bare bones, static routes
		-
```
const express = require('express');
const app = express();
const port = 3000;

// Route
// (URI, req/res callback)
// static route for static content
app.get('/', (req, res) => res.send("hello"));

// Activate server
// port, optional callback
app.listen(port, () => console.log(`PORT: ${port})`);
```
- ## Getting parameters (req.query vs req.params)
  - ### `req.query`
    - optional parameters
    - specified in URI using keyword
      - `/hello?firstName=david&lastName=mavis`
      - Order doesn't matter
      - keys are case sensitive
    - Access values using `req.query.<VAR_NAME>`
```
//example url: localhost:8000/hello?lastName=mavis&firstName=david
app.get('/hello', (req,res) => {
    // object of values passed through url
    console.log(req.query)
    const firstName = req.query.firstName; //david
    const lastName = req.query.lastName; //mavis
    
    // page will be sent regardless of if any parameters were passed
    // parameters that are missing will be 'undefined'
    res.send(`<p>Hello ${firstName} ${lastName} ! ! !</p>`);
    
})
```
  - ### `req.params`
    - parameters are a path in the URI
      - `/goodbye/<PARAM_1>/<PARAM_2>`
      - Order matters
    -
```
app.get('/goodbye/:firstName/:lastName', (req, res)=> {
    let firstName = req.params.firstName;
    let lastName = req.params.lastName;
    res.send(`<p>Goodbye ${firstName} ${lastName} . . .</p>`);
})
```
  - ## Serving a lot of static content
    - ### `express.static()`
      - `app.use(express.static('public'));`
      - Tells express to serve files from the directory `./public`
      - Gets files based on URI
        - `localhost:8000/static_world.html` -> `./public/static_world.html`
  - ## Serving a lot of dynamic content
    -
    - Use `.ejs` files inside `views` directory
      - can also be a path in `views`
    - Use `<%= VARNAME %>` in `.ejs` to access variables
			
```
// Tell express app to use ejs as the view engine
app.set('view engine', 'ejs')

app.get('/dynamics', (req,res) => {
    // res.render, NOT res.send!!
    // looks for 'dynamics.ejs' inside dir 'views'
  res.render('dynamics', {
      //this data is passed to ejs
      dateVar: new Date()
    })
})
```
  - ## Getting input from fields
    - Create a form
      -
```
<H1>FOURM</H1>

<body>
    <form action="/form" method="POST">
        <!--- `name=` defines what the variable is called --->
        <input type="text" name="name">
        <input type="password" name="password">
        <input type="submit" value="send">
    </form>
</body>
```
  - **IMPORTANT**: Put this line in your code: `app.use(express.urlencoded({extended:true}))`
  - Create a route using `app.post`
    -
```

app.post('/form', (req,res) => {
    // get input from page using req.body.<NAME>
    const password = req.body.password;
    if (password === 'start') {
        res.render('hello', {
            name: req.body.name
        })
    } else {
        res.send('static_world.html')
    }
})
```
			-
			-
