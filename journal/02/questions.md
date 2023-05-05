# Intro to JavaScript
01. Which keywords are used to declare a variable in JavaScript?

    > Var, Let, and Const

02. What is the definition of a function?

    > A function is a defined program designed to perform a particular task.
    Its basically a stored block of code that can be invoked and called.

03. What are the `SOLID` principles?

    >single responsibility: when writing something like a function. You should not make a single function responsible for many different things.
    It is often better to create a function that does one thing then calls for another function to do another thing.

    >open-closed principle: As you develop your site, things change. Creating a class that can be extended upon is much better than changing the class itself.

    >liskov substitution principle: Its basically the idea that as you change something in your code, your going to need to factor in the rest of the code that is impacted by that change.

    >interface segregation principle: Avoiding the use of one big generalized interface over smaller specific ones.

    >dependency inversion principle: Make your code depend on abstractions over concretions. It will make it more flexible and reusable. 


04. Given this array: How could you remove the `pineapple`?

    ```js
    let fruit = ['apple', 'banana', 'pineapple', 'orange', 'strawberry']
    ```

    > fruit.splice(pineapple)

05. Given these two objects: How could you add each to the others friends arrays?

    ```js
    let you = {
        name: "You",
        hair: true,
        friends: []
    }
    let them = {
        name: "Them",
        hair: false,
        friends: []
    }
    ```

    > them.friends.push(you.name, you.hair)
    > you.friends.push(them.name, them.hair)

06. Give an example of a JavaScript `Conditional`:

    > let x = 1
    > let y = 2

    if (x == y){
        console.log('x is equal to y')
    }
    <!-- nothing will show up in the console because x is in fact NOT equal to y -->

07. What is the main difference between `parameters` and `arguments`?

    > Parameters are names created for functions. Arguments are values given to the function to invoke it.

    basically, if a function is given a parameter, it cannot be invoked until the function is given the proper argument that meats the requirements of the parameter.

08. Instead of writing everything to the console, what is a better way to debug your code?

    > A potential way is to use debugger on a function to debug it through dev tools.

09. What is the difference between a `primitive` value and a `reference` value?

    > A primitive value can be undefined, null, boolean, number, or string.
    > A reference value is an object with primitive value properties.

10. Demonstrate a loop that prints the numbers between -100 and 100?

    >  for (let i = -100; i <= 100; i++){
        console.log(i);
    }
