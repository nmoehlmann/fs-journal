If the launch file doesnt show up, use dotnet build. Also dotnet restore.

Nuget is basically the npm for dotnet which connects your server to the mongo database through dotnet.

# NOTE 

uuid4 is a id generator

tinyint uses 0 and 1 truthy falsy values. could use boolean or tinyint.

when dropping tables its safer to drop them in the reverse order in which they were created. drop the many to manys first.

instead of using null as default value for model data. use .length == 0 to check for the same thing. big brain check

never put s in the wrong spot. When we use a prop we arent ever getting more than one of that thing.

cntrl d if you want to select the same word on the same row.

a 405 is when the route request is correct but the request method (post, get, put, etc..) does not exist in backend.

you can select an entire row back with FROM LAST_INSERT_ROW() method.

can use var to declare a variable. c# thing. its the difference between implicit and explicit type.

can use v-if and v-else to create a loading screen before the restaurant actually exists. think this only works on objects but idk

where is filter for c#

You can call functions in the auth service so that you only get things after the account is authenticated. very good for getting MY stuff and account related things.

on buttons, type="reset" clears the form it is in.

.FirstOrDefault returns one object. the Query gives a list so we use that method to return only one thing. first method will give back one thing as well but if the array returns empty then it will throw an error.

when trying to compare a property on two different objects that have the same name, you will get an error. You must alias it out and then use the property so SQL knows which is which.

if you use setup in the script: <script setup>, you can use const props = defineProps({}) and then put props inide the props.

the title attribute puts a tooltip on the given element. cool

you can put properties in the modals that arent in the database. these properties can be populated and virtualized in the repo.

we can use a COUNT to basically only get a certain number back determined by a conditional SQL. we use this to get the reports. we use LEFT JOIN because we dont want to join anything that isnt the id that we are comparing.

can use emitters to execute functions when they are triggered. its a listener.


# backend

# Get All Resaurants

Create function in page, service. Get SOMETHING back

create a restaurant card to put the data on with v-for.

# Post resaurant

because we are already on the front end. we simply create a form ez pz

throw the form on the dom and make the post function in the component.

we go to service to create post function.

# post rs backend

now we go into the backend to write out the rest of the function.

we start in repo. we create and select using thing on line 21

we move to the service. ez pz

we move to controller.

# get active front end

we want to get the restaurant that you click on. we create the fuction on the front end.

# get by id on back end

Now that we wrote the function on the front end we need to finish it on the back end.

can technically get back data in the controller but we dont want to do it that way, that way is BAD.









