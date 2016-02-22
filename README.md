# JavaScript Objects
So what is an Object in Javascript?

JavaScript is an object oriented programming language. Everything can be described by objects, which bundle properties with methods and events that impact those objects.

An object is a list of associated data pairs. Unlike arrays, objects do not have numbered indexes. Instead they contain key names and associated values. Where a numbered grocery list is a good metaphor for an array, a birthday list including a person’s name (key) and their birthday month value) would be a better metaphor for an object.

```
> var birthdays = { "Homer" : "August", "Marge": "October"}
```


Objects are like an unordered list of pairs. The syntax is different, too.

```
> var fruitColors = { "apple" : "red", "tangerine": "orange", "banana": "yellow"}
```
`apple` is the key, and the associated value is `red`


You can find a value by indexing an object using the key.
```
> fruitColors["apple"]
You will get an error if you ask for something that doesn't exist.
> fruitColors["pear"]
```
Javascript also allows you to access the values by using dot notation.

```
> fruitColors.tangerine
```

You can also reassign values.

`fruitColors["apple"] = "green"`

Finally, you can use Object.keys() to list all of the keys in an object.
`Object.keys(fruitColors)`


## Methods in JavaScript Objects
In real life, a person is an object. A person has **properties** like firstName, surname, age, and gender. A person's ability to express her thoughts can be defined as a **method** _talk_. These properties will be the keys to our person object.

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

      To access the value inside our person object, you can use dot notation or index the object using the key for the property you want.
      ```javascript
      person.firstName
      Jane
      person["age"]
      24
      ```
      To use a method within the object, just use dot notation.
      ```javascript
      person.talk()
      "Hello, my name is Jane"
      ```
