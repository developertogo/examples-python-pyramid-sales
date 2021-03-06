examples-python-pyramid-sales
=============================

d3.js linear graph of 'Sales over Month' data fetched from a web server running Pyramid with SQLAlchemy ORM connected to a PostgreSQL DB.

Go to: http://pyramid-sales.herokuapp.com/ to see the app in action.

Sales over Month App - README
=============================

Objective
---------

Demonstrate understanding of the in/out's workings of the Python [Pyramid Web Framework](http://www.pylonsproject.org/) with SQLAlchemy.)

Project
-------

Display a linear graph of sales over time (y-axis is $, x-axis is month).
Create dummy/static data, but load the data via an ajax call.

Strategy
--------

*   Select an elegant front end graphic library, d3.js
*   Data is randomly auto-generated and stored in the DB
*   Data is fetched via an ajax call, e.g. http://pyramid-sales.herokuapp.com/sales_month, 
    to select the data from DB and pass to the front end for display
*   Unit test the workflow
*   Setup Pyramid directory structure for models and views so that new functionality is easily added
*   Select Mako templating for its inherintance features
*   Deploy app to Heroku with a Postgres Add-on

Getting Started
---------------

*   git clone or download it to your local system.

*   install & setup postgresql
   
        On Ubuntu, you do (use the equivalent cmd in your linux env):
            sudo apt-get install postgresql
    
        Basic setup (create user: root with password: root and database: sales)
            sudo -u postgres createuser root
            sudo -u postgres psql
            postgres=# \password root
            sudo -u postgres createdb -O root sales

Note: $venv is 'your virtual env'

*   cd 'directory_to_this_app'

*   install require packages
  
        $venv/bin/python setup.py develop

*   initialize the db creating a 'sales_month' table if it does not exist and inserting random values
    
        $venv/bin/python initialize_sales_db development.ini

*   run the unitest
    
        $venv/bin/python setup.py test -q

*   start app
    
        $venv/bin/pserve development.ini

Using d3.js to fetch the data via an ajax call and display the sales-month line graph.
