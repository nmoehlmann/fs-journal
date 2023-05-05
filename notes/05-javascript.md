# JavaScript

# Ternary

example: num % 2 == 0 ? 'even' : 'odd'

conditional, 1st returns if true and 2nd returns if false.

# DataTypes

strings:

""; double quotes
''; single quotes
``; backticks

numbers:

1 2 3
-1 -2 -3
.5

Boolean:
true
false

the weird ones:
undefined
null
NaN

Objects:
{}
Object

Arrays:
[]
Array

# General

## alerts suck
throw new Error("") throws error when condition is met: stops function
return: stops function

# function layout
Usually calls to do something if it gets past a bunch of false conditionals.

# Maths
Math.ceil rounds up
Math.floor rounds down
math.random gives random number between 0 and 1

# targeting in JS

document.getElementById('').innerHTML = `${heroHealth > 0 ? heroHealth: 'skull-emoji'}`

# Loops



# Arrays

can put objects in an array


# Functions
 

this clue has already been given, so it stops.
if (givenClues.includes(clueKey)) {
  return
}

if you use a ternary it is using if else if else conditionals. meaning it wont continue if one condition is met because of the else.

## placeholder
the parenthesis in a function are the parameter.

the more you write in the parameter the more you will need to invoke the function.

function whatever(x,y,z) needs to be supplied with an x and y and z to be invoked.

be default the parameter's data type is any. but the data type can be changed with "@param {string} placeholder" for example.

/** to create param for function.

## parameters

basically used when we dont know what content we want to be used.

you pass arguments into parameters to invoke functions.

The argument is usually given in HTML
The parameter is usually in the JS

# Templates

example:
sandwiches.forEach(s => {
  if (s.quantity > 0){
    template += `
    <div>hi</div>`
    }
  }
})

"sam", 'sam', `sam`, all strings

# querySelector

can be used to select an element from html.

# offset

can use offset in a col to take up the empty space
example: <div class="col-4 offset-2"> takes up the 2 out of 6 spaces inside col.

# switch

ex: switch(animal.mood) {
  case "the value of mood":
    income += 50
}

the switch is the value and the case is what the value is being compared to.

default will run if no other case is met and acts as a return.




