# JavaScript Objects
Up to this point we've learned about arrays, which were described as buckets that can store multiple variables of mixed data types. Arrays are ordered lists, and can be accessed with a numeric index.

```js
var teams = ["Cubs", "Mets", "Dodgers", "Giants"]
teams[0] = "Cubs"
```
In fact, because an array is a collection of elements, arrays are actually simple objects. Objects are a place to store multiple values of any type, including methods. Each value is an associated data pair, a key and a value. Below, the monster object has four key-value pairs.

```js

var monster = {fur: "blue", eyes: 4, claws: true, emotions : ["confused", "happy", "peaceful"] }

```

##Objectives
* Object Syntax
* Accessing Object Properties
* Object Literals vs Object Constructors
* Methods in Objects
* JSON Introduction


##Object Syntax
Notice that objects start with a pair of curly brackets. Each key and value pair is separated by a colon. `apple` is the key, and the associated value is `red`.

```js
var fruitColors = { "apple" : "red", "tangerine": "orange", "banana": "yellow"}
```

##Accessing Properties
Objects are stored in key-value pairs and don't have an order. So instead of indexing with numbers, you can find a value by indexing using the key.
```
> fruitColors["apple"]
red
You will get an error if you ask for something that doesn't exist.
> fruitColors["pear"]
undefined
```
Javascript also allows you to access the values by using dot notation.

```
> fruitColors.tangerine
orange
```

You can also reassign values.

`fruitColors["apple"] = "green"`

Finally, you can use Object.keys() to list all of the keys in an object.
`Object.keys(fruitColors)`

##Object Literals vs Object Constructors

In the previous examples, we wrote our objects (monster and fruitColors) out all at once. This type of syntax is called an object literal. In object literals, the property keys and values are defined as the same time that the  object is created. Below we create just one pizza.

```js
var pizza = {toppings: ["pepperoni", "bacon"],
             size: "small",
             customer: "Michelangelo",
             price=12,
             discount=.10}
```
A lot of the power from objects comes from when they act like a blueprint, to create copies of things that would have the same properties. For example, if we know we'll be storing multiple pizza orders we can use the  constructor function.

The object constructor function takes in as many parameters as there are properties. It then can act upon those parameters using the keyword `this`, which holds the place of whatever new object is currently being created.

```js
function pizza(toppings, size, name, price, discount) {
    this.toppingsList = toppings;
    this.pizzaSize = size;
    this.customer= name;
    this.finalPrice = price - (discount * price)
}
var pizza1 = new pizza(["bananas", "jelly beans", "peanut butter"], "large", "Donatello", 20, 0);
var pizza2 = new pizza(["anchovies"], "medium", "Raphael", 15, .15 );
```
We can make as many pizzas as we want and the pizza() constructor will create a new pizza object with the properties toppingsList, pizzaSize, customer and finalPrice.
```js
>pizza1.toppingsList[1]
"jellybeans"
>pizza2.finalPrice
12.75
```
## Methods in Objects
The final powerful component of objects are their ability to store methods as properties.
When we describe our friends, we might describe their characteristics, but also the things that they do.

Object  | Property Name        | Property Value                    | Method |
----------|---------------------------|-------------------------------------|-------------|
person | firstName                | person.firstName = "Jane" |
            | surname                 | person.surname = "Doe"    |
            | age                         | person.age = 24                 |
            | gender                    | person.gender = "Female" |
            |                                |                                            | person.talk();


Using this representation of person, every person object in JavaScript will have the same property names (firstName, surname, age, and gender) **BUT** different property values. Each person object would also have a method _talk_.

Let's fill out the profile of our `person object` to match the information in the object table above:

```javascript
      var person = {
        firstName: "Jane",
        surname: "Doe",
        age: 24,
        gender: "Female",
        talk : function() {
         return "Hello, my name is "+ this.firstName;
         }
        }
```

To use a method within the object, just use dot notation.
```javascript
>person.talk()
"Hello, my name is Jane"
```
##JSON Introduction
Later in the prework you will learn more about JSON, which stands for JavaScript Object Notation. JSON takes advantage of both the organized way that objects store large collections of data and the ease of accessing that data. For these reasons, JSON is a popular way to store and send large amounts of data.

##Conclusion
Objects are the holy grail of JavaScript. Objects can store a lot of different types of information in an organized, modular way. Objects are what give JavaScript it's flexibility and power.
