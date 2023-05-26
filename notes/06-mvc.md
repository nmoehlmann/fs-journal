# MVC

# Class

a class is defined, then a constructor is made to define an object.
example:
class Hero {

@param {{name: string, health: number, level: number}} data

  constructor(data) {
    this.name = data.name
    this.health = data.health
    this.level = data.level
  }
}

variables created in a js file is locally scoped.

# controller

IT IS NEVER THE JOB OF THE CONTROLLER TO MODIFY DATA

# order to follow

setting up files.

## MODELS
models: setting up what our data looks like. always creating a new file.
> Exporting and Importing. must export class to reference it in other places.
>Classes do not use (), only {}.
>Constructor: what is invoking the class that it is in. This uses ().
must use this.'key' in order to define constructor variable.

>when calling a class you use: new "class name" ({any key value pair inside the class})
>Constructor sets a parameter through the parenthesis. It defines key value pairs inside the {}.

>getter: can create templates.

## AppState
>the class and model is what i want my data to look like. but the AppState is where that data is stored.
>Here we can place the new classes and put in some parameter data for each new class.

>We can use an @type to note what an array should have in it. documentation like @type is important but probably not required.

>should not be responsible for anything other than where data lives.
## Service
> dont want to give access to entire class, so only export a single class to be used elsewhere.

## Controller
>this is the filter between the user and the rest of the application. anything a user can interact with will come through the controller first.

> If we want something to happen immediately after the file is mounted, you put it in the constructor.
> things that are outside of the exported class will be private data that can only be used by the controller.

>Any function created with an _ before it is a 'private function'. its not required but is industry standard.

>A block of code outside of a class is a function. if you are creating a function inside of a class, you cant use function. It becomes a method.

>when using setHTML(): setHTML('id', 'the template')  

>using .on is basically an event listener that performs an action if something changes.
 

## App.js
> this is actually linked via a script file inside the html. this is then linked to the controller 

# MVC general:
>Only time we ever export something is when we arent using a class.

## getter
>inside the 'Car.js' we set a bunch of data in the constructor so that we can utilize it with the getter. this.year = data.year. we are pulling data.year from the AppState and setting it within this.year.

# MVC AUTH

paste key stuff in the env.js file. domain, audience, clientID.

base URL swap to sandbox webpage url.

the auth token is the accounts id.

## router.js

basically tells the application which controller to use depending on which page you on.

# api stuff 
 
when pulling api data the objects that are "required" are necessary or it will throw error.



#  Backend stuff

# package.json
dependencies are all of the external libraries included.

> "npm i" installs all the dependencies for particular project.
>  

gets dont have bodies / posts and puts do 


# account user info  

user is auth0 data base, account is users data base.

mongoose.model('car', CarSchema) first one is making it is the data base, the second is declaring it. 

