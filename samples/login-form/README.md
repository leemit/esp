login-form Sample
===

This sample shows how to configure a simple form-based login using ESP. 
This sample uses the a web form for entering username and password credentials.

This sample uses:

* Https for encryption of traffic for login forms
* Redirection to a login page and logged out page
* Redirection to use https for login forms and http once logged in
* Self-signed certificate. You should obtain a real certificate.
* Login username and password entry via web form
* Automatic session creation and management
* Username / password validation using the "config" file-based authentication store.
* Blowfish encryption for secure password hashing

Notes:
* This sample keeps the passwords in the package.json. The test password was created via:

    esp user add joshua pass1

* The sample is setup to use the "config" auth store which keeps the passwords in the package.json file.
    Set this to "system" if you wish to use passwords in the system password database (linux or macosx only).

* Session cookies are created to manage server-side session state storage and to optimize authentication.

* The sample creates three routes. A "public" route for the login form and required assets. This route
    does not employ authentication. A default route that requires authentication for access. And a
    action route for the login controller that processes the login and logout requests.

Requirements
---
* [Download ESP](https://embedthis.com/esp/download.html)

To run:
---
    esp run

The server listens on port 4000 for HTTP traffic and 4443 for SSL. Browse to: 
 
     http://localhost:4000/

This will redirect to SSL (you will get a warning due to the self-signed certificate).
Continue and you will be prompted to login. The test username/password is:

    joshua/pass1

Code:
---
* cache - Directory for cached ESP pages
* controllers - Directory for controllers
* documents/public - Web pages and resources accessible without authentication
* documents - Web pages requiring authentication for access
* [documents/index.esp](documents/index.esp) - Home page
* [documents/public/login.esp](documents/public/login.esp) - Login page
* [controllers/user.c](controllers/user.c) - User login controller code
* [esp.json](esp.json) - ESP configuration file

Documentation:
---

* [ESP Documentation](https://embedthis.com/esp/doc/index.html)
* [ESP Configuration](https://embedthis.com/esp/doc/users/config.html)
