# Application Architecture, MVC Design Pattern
01. What are the Pillars of Object Oriented Programming (`OOP`)?
  
  > Abstraction: To have functionality that can be used for more than once in the code.

  > Encapsulation

  > Inheritance

  > Polymorphism

02. How does `export` differ from `export default`?
  
  > Export default only allows you to export a single value from a module, whereas a named export allows multiple values to be exported.

03. What is Encapsulation?
  
  > Encapsulation is the idea that code should be stored in separate files depending on what they do and how they are handled. Private fields are scoped to the file they are in, and code in these fields cannot be used anywhere outside of the file.

04. What are some of the benefits of the `Proxy` object that we are using in our structure for applications?
  
  > Proxies can be used to prevent sensitive data from being accessed anywhere other than the file its on.

05. What the difference between a `class` and an instance of a `class`?
  
  > A class is used to store a constructor and methods data. an instance of a class will always be used in a separate file from the original in order to access that classes data.

06. What is a computed Property?
  
  > A property that can be accessed from other stored properties.

07. What is the purpose of the `MVC` pattern?
  
  > The MVC pattern is a data structure designed for complex application.s It uses multiple levels of code that all have distinct access to eachother's data.

08. What is the job of the `Controller` in the `MVC` Pattern?
  
  > The controller is responsible for dealing with the user's inputs and interactions with the application.

09. What is the job of the `Service` in `MVC`?
  
  > The service takes inputs from the controller and directly manipulates the data in the app state.

10. What is the job of the `Model` in `MVC`?
  
  > The Model is what the data looks like in the application. This base model for the data is defined and stored inside the app state.
