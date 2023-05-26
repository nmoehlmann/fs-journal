# Intro to Server side concerns with JavaScript
01. What do the letters of the acronym `CRUD` stand for?

  > CRUD
  C: create - post
  R: read - get
  U: update - put
  D: delete - delete

02. Each action that `CRUD` represents maps to an HTTP request. What HTTP request does each `CRUD` action correspond to?

  C: create - post
  R: read - get
  U: update - put
  D: delete - delete

03. What does `ORM` stand for? Which `ORM` do we use when interacting with MongoDB

  > Object Relational Mapping
  we are using mongoose to create a relationship between collections in our database

04. Which two `HTTP` request types include a body?

  > Post and Put requests include a body. 

05. In a/an ______ coding model, when you call a function, it returns only when the action has finished and stops your program for the time the action takes. Likewise in a/an _______ coding model, multiple things are allowed to happen at one time. When you perform an action, your program continues to run.  Fill in the blanks.

  > 1: Synchronous
  > 2: Asynchronous

06. What are the three types of data relationships? Provide an example of each.

  > single to single
  > single to many
  > many to many

07. What is middleware?

  > middleware allows the communication and translation of data between our database and application.

08. The request request delivers information from the client while the response pipeline returns it. Fill in the blanks. 

  > Request, Response.

09. Demonstrate the pattern that is used to include a request query with the client's `HTTP` request providing the property `tag` and the value `winter`.

  > http://localhost8080/api/houses/?tag=winter

10. What is a ***virtual property***?

  > the virtual property is used to append objects in two separate collection to share a relationship. when an object from the database is requested using a get method, it will show up on the front end. when that object is populated using a virtual property on the backend, it will show related data from other collections.
