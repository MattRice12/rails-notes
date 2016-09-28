TDD Steps:
  1) Write a failing test first
  2) Only write enough code to make that test pass
  3) Write another failing test
  4) Refactor to make those tests pass

SOLID:
  1) Single Responsibility -- one reason to change
  2) Open/Close Principle -- classes should be open for extension / close for modification
  3) Liskov Substitution Principle -- subclasses are interchangeable with their parents, but not vice versa
  4) Interface Segregation Principle -- build your own code to act as an intermediary between you and another interface
        So if you need to change the interface, you don't have to rewrite your code
  5) Dependency Inversion Principle -- Higher-level abstractions should not depend on lower-level concepts.
        You should be passing in your dependencies instead of having them concretely established.

KISS: Keep it Simple, Stupid

OO -- Object Oriented Programming
  1) A way to model the real world by encapsulating behavior and state into objects and methods (and classes)
  2) Encapsulation, Isolation, && Inheritance
    Cohesion -- how classes work together balanced with coupling (balance between being interdependent and completely dependent)

Functional Programming -- Focus on pure functions and the removal of mutable state (changeable variable)
  Pure function -- A pure function is a function where the return value is only determined by its input values, without observable side effects.
    EXAMPLE: length(s), returning the size of a string s

REST -- REpresentational State Transfer
  The idea that a url should represent a state of an application and return back the same result of the same resource.

HTTP -- Hyper Text Transfer Protocol
  The method we use for communication on the web.

everything after '?' in a URL -- query parameters

Train Stops on the Rails
  Routes >> Controller >> Model >> Database >> .... >> Model >> Controller >> View/Data

MVC -- Model | View | Controller
  Separation of Concerns

SQL -- Structured Query Language -- how we communicate with our Database (DB).
  We use postgresql -- it is a structured relational DB (i.e., using rows, columns, and tables)
  Tables:
    Primary keys -- a unique value used to find records.
    Foreign keys -- a primary key on a foreign table used to connect tables.
    Join Query -- a way of combining sets of two disparate tables together to be able to query against the tables
      SQL queries are dealing with set theory.

Active Record (AR) -- the Object Relational Mapper (ORM) we use in rails.
  We write AR queries that convert into SQL strings that run against the DB.
  AR Relations: has_many, belongs_to in our models are markup for what is already true in our DB
  Rails is not smart/magical; Rails makes good guesses, occasionally.
  has_many_through -- a join query connecting tables through a table.

Active Record Callbacks
  before_validate  after_validate
  before_save         after_save
  before_create       after_create
  before_update       after_update
  before_commit       after_commit
  before_destroy      after_destroy
  after_initialize

CRUD -- Create, Read, Update, Destroy
  Index, Show, New, Create, Edit, Update, Destroy
  Ruby methods when written in a controller are called actions

HTML --
  Write ruby code with ERB tags (<% %> / <%= %> / <%# %>)

Partials -- a way of reducing HTML duplication
  All partials start with an underscore(\_)

Helpers -- Methods that can be used in the View layer of rails
  All helpers in rails share a global namespace (so be careful!)

Sass -- CSS PLUS -- a pre-processor for CSS
  Gives us:
    1) nesting
    2) variables
    3) mixins
    4) partials
    5) functions & loops

JavaScript - NOT JAVA
  It is Cool?
  It allows us to add interactivity to our webpages (makes our static webpage dynamics)
  It allows us to use AJAX
    Asynchronous Javascript and XML (though it uses XML, we primarily use JSON as our transfer type)
  React -- A JavaScript library for building user interfaces (UIs). It simplifies front-end

jQuery -- A JavaScript Library for manipulating DOM and other stuff.
  Main Purpose -- for cross-browser compatibility. The same jQuery will work for every browser out there.

Vanilla JS -- the most performant JS ever.

Agile -- a software development methodology.
  Agile focuses on people not on processes and on working software over comprehensive documentation.

SCRUM -- it is a set of processes built on top of Agile to help teams get their work done.
  Deals with the idea of having:
    1) Stand-ups -- meetings with the entire team to go over the most recent work
       Each team member talks.
    2) Sprints/Iterations -- These are a period of time (1-4 weeks) where people are working on an agreed upon set of user stories. At the end of the sprint, the work gets deployed into production.
    3) User Stories -- part of an agile approach that helps shift the focus from writing about requirements to talking about them.
       All agile user stories include a written sentence or two and, more importantly, a series of conversations about the desired functionality.
    4) Estimates -- Most Agile shops will put estimates on their work. Estimates are organized into points with "1" being the smallest amount of work to be done.
    5) Automated Testing -- Agile shops will use a variety of testing practices to verify that their code will do what their stories say it should be doing.
__________________________________________________________________________
