Chitteruby!
=================

A Twitter clone built using the Sinatra Ruby gem and Embedded Ruby.

Challenge:
-------

```
STRAIGHT UP

As a Maker
So that I can let people know what I am doing  
I want to post a message (peep) to chitter

As a maker
So that I can see what others are saying  
I want to see all peeps in reverse chronological order

As a Maker
So that I can better appreciate the context of a peep
I want to see the time at which it was made

As a Maker
So that I can post messages on Chitter as me
I want to sign up for Chitter

HARDER

As a Maker
So that only I can post messages on Chitter as me
I want to log in to Chitter

As a Maker
So that I can avoid others posting messages on Chitter as me
I want to log out of Chitter

ADVANCED

As a Maker
So that I can stay constantly tapped in to the shouty box of Chitter
I want to receive an email if I am tagged in a Peep
```

Notes on functionality:
------

* You don't have to be logged in to see the peeps.
* Makers sign up to chitter with their email, password, name and a username (e.g. samm@makersacademy.com, password123, Sam Morgan, sjmog).
* The username and email are unique.
* Peeps (posts to chitter) have the name of the maker and their user handle.
* Your README should indicate the technologies used, and give instructions on how to install and run the tests.

Bonus:
-----

If you have time you can implement the following:

* In order to start a conversation as a maker I want to reply to a peep from another maker.

And/Or:

* Work on the CSS to make it look good.

Technical Approach:
-----

My initial approach to the bankend functionality was to follow the Model, Repository and Database connection class framework to implement the programs core functionality.

View the ```recipe.md``` file for further notes and details on how I approached this project.

Within the app.rb file, the Sinatra Ruby gem is used to establish routes and determine which HTTP requests the application can respond to.

I took a much more hands on approach with creating the routes after doing a basic outline which can be viewed within the ```routes_recipe.md``` file.

## Installation 
Run the below from the command line:

```
git clone https://github.com/MattHammond94/Chitteruby.git
cd Chitteruby
bundle install
```

You will then need to create a database and create the tables within the database:

```
createdb chitter_base
psql -h 127.0.0.1 chitter_base < ./spec/table_design_seeds.sql
```

You will also need a seperate database for running/creating tests in the spec files.

```
createdb chitter_base_test
psql -h 127.0.0.1 chitter_base_test < ./spec/table_design_seeds.sql
```

You can then run ```rspec``` to view the current test coverage of 100%

Note - If you wish to use different database names then you will need to change change the current conditional branches at the top of the ```DatabaseConnection``` class (See lines 6 and 8.)

## Running the program

To run the program run ```rackup``` from the command line and then visit ```http://localhost:9292/``` in your chosen web browser.

## Notes

Personal review:

I wanted to jump straight into the project after completing my design recipe for how the database would work/interact with the repo classes so I only gave a short overview to how the routes would work and this can be referenced in the “routes_recipe.md” file.

I quickly became intrigued by new ideas and new features as I was working through creating the routes which meant my test driven approach became somewhat sloppy and less structured.

Also because of this my commits also became relatively fast and loose and not as structured as they have been on previous projects.

Still to do:
* General design/look - Learn and apply more CSS.
* Reformat the way the time/date is shown.
* Add Further tests to control user input.
* Look into 'Cost' with Bcrypt to resolve tests functioning slowly.
* Look into potential bugs as per notes in spec files.
* Go back and research database joins - use this knowledge to implement comments on peeps
* Add a route to the user page for removing an account - implement a piece of JS to warn the user that if account is removed all peeps will go with it.
* Add some regex to control password and email acceptability - Make passwords more secure.
* Update and include diagrams in my route recipe/design
* IMPORTANT - DEPLOY
* For fun: Maybe add some censorship(just because)
