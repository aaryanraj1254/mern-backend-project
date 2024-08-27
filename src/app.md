<script>


The code starts by importing several modules:

express: a popular Node.js web framework
path: a built-in Node.js module for working with file paths
hbs: a template engine for rendering HTML templates
bcryptjs: a library for hashing and salting passwords
jsonwebtoken: a library for generating and verifying JSON Web Tokens (JWTs)
Register: a Mongoose model for interacting with the registers collection in the MongoDB database
Setting up the Express app

The code sets up an Express app and configures it to:

Use JSON parsing middleware to parse incoming requests with JSON bodies
Use URL-encoded parsing middleware to parse incoming requests with URL-encoded bodies
Serve static files from the public directory
Set the view engine to hbs and the views directory to templates/views
Register partials for the hbs template engine
Defining routes

The code defines several routes:

/: renders the index template
/register: renders the register template
/login: renders the login template
/register (POST): creates a new user in the database and generates a JWT token
/login (POST): checks the user's login credentials and generates a JWT token if valid
Creating a new user

When a user submits the registration form, the code:

Checks if the passwords match
Creates a new Register document with the user's data
Generates a JWT token using the generateAuthToken() method
Saves the user document to the database
Redirects the user to the index page with a 201 status code
Logging in

When a user submits the login form, the code:

Finds the user document in the database by email
Checks if the password matches using bcrypt.compare()
Generates a JWT token using the generateAuthToken() method
Redirects the user to the index page with a 201 status code if the login is valid
Error handling

The code catches any errors that occur during the registration or login process and returns a 400 status code with an error message.

Starting the server

Finally, the code starts the Express server on port 3000 and logs a message to the console indicating that the server is running.

Note that the code also includes some commented-out sections that demonstrate how to use bcryptjs and jsonwebtoken separately. These sections are not part of the main application logic.




