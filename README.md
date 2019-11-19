# Qdus-Michael-Eritrean-Orthodox-Tewahdo-Church-in-Santa-Rosa-CA# Qdus-Michael-Eritrean-Orthodox-Tewahdo-Church-in-Santa-Rosa-CA
CHURCH  DATA APP
App for making bookings of time serves , administrating facilities and summarizing bookings father servis or church progaram  for each serves 

Developer
filmon Habtu - CSS / Bootstrap
Filmon Habtu - HTML / Handlebars
Filmon Habtu  - API Routes / Presentation
Filmon Habtu  - Models / Logic
Who, What are they doing,
Concept
church data app is a app and website that helps eliminate the common problem associated  solutine  servis they need 

Features:
Front End:
Entry Interface: There will be an entry interface which allows the operator to “book” a facility for a bord manbare on a set day and time frame. serves day donation paymant monthely paymant youth progrma  The interface will also allow you to update and delete the entry if needed.

church app Chooser Interface: This interface will display all of the church app  as individual buttons. When the user chooses  church app the screen will go to a separate URL where we pass the :church app Name to the API to display the information on the people who rented the facility.

church app  Display Screen: This screen will allow the user to choose a date and will then display the information of all of the parties that have rented that church app  for that chosen day.

Technologies:
Javascript
Express
Sequelize
Handlebar
Bootstrap
cookie-session (new technology, allows login sessions to be created)
New technology - sessions
This uses

A detailed explanation can be found at Sessions



Heroku deployment


Git hub repository


Build development environment
clone the master repo, cd to recBooker directory

npm install will install all the node modules

create a .env file (not tracked by git) and add the following using editor

DEV_MYSQL_USER="<your user name for mysql server>"
DEV_MYSQL_PASSWORD="<your password to mysql server>"
NODE_ENV ="development"
Initialize mysql server: (only needs to be done once)

Use mysql workbench to load and execute the following files

db/databaseSchema.mysql
db/testDatabaseSchema.mysql
or use mysql at command line

mysql -u root -p
Enter password: **********
....
mysql>
mysql> source db/databaseSchema.mysql;
mysql> source db/testDatabaseSchema.mysql;
mysql> exit
to clear database and seed it, add

DEV_MYSQL_FORCE_DB_RESET=0
to .env file

to run application node server or npm run start

Continuous integration and linting
detailed setup guide

eslint
.eslintrc.json modified to support es6 syntax
.eslintignore ignores anything in node_modules or test directories. Ignoring test is necessary because eslint not supporting mocha (may get fixed later) Eslint can be run on a single file with either of the following
npx eslint <file>
npm run lint <file>
Travis
Travis links into the github repo and runs based on the configuration file .travis.yml It runs every time something is checked into the github master. Can check other branches by adding the branch name to the branches: only: field.

It runs the

"scripts": { test: "npm run lint && cross-env NODE_ENV=test mocha test -u bdd --reporter spec --exit" }
command. This runs eslint on all .js files in the directory (other than those in .eslintignore ) and in parallel runs all the mocha tests in the test directory.

You should check for compliance before making pull request by running

npm test
which runs the same code in your local environment

File structure
(excludes .git/ and node_modules/)

|--church app 
    |-- .env
    |-- .eslintignore
    |-- .eslintrc.json
    |-- .gitignore
    |-- .travis.yml
    |-- API_DEFINITION.md
    |-- package-lock.json
    |-- package.json
    |-- README.md
    |-- server.js
    |-- config
    |   |-- config.json
    |-- db
    |   |-- databaseSchema.mysql
    |   |-- seed.mysql
    |   |-- testDatabaseSchema.mysql
    |-- models
    |   |-- example.js
    |   |-- index.js
    |-- public
    |   |-- js
    |   |   |-- index.js
    |   |-- styles
    |       |-- styles.css
    |-- routes
    |   |-- apiRoutes.js
    |   |-- htmlRoutes.js
    |-- test
    |   |-- canary.test.js
    |   |-- mocha.opts
    |   |-- modelTester.js
    |   |-- functions
    |       |-- executeSQLFile.js
    |-- views
        |-- 404.handlebars
        |-- example.handlebars
        |-- index.handlebars
        |-- layouts
            |-- main.handlebars
