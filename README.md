1) Imagine that you have two classes named "Animal" and "Dog" and you want the class "Dog" to have all the properties and methods from the class "Animal", how would you do it? How is this called? What's the benefit?
* The derived class inherits the features from the base class.
For example -
```
class Animal {
    // eat() function
    // sleep() function
};

class Dog: public Animal {
    // bark() function
}; ```

** Here, the Dog class is derived from the Animal class. Since Dog is derived from Animal, members of Animal are accessible to Dog.

* the use of the keyword public while inheriting Dog from Animal.
```class Dog: public Animal {...};```

* Inheritance is an is-a relationship. We use inheritance only if an is-a relationship is present between the two classes.

Example -
``` // base class
class Animal {

	public void eat() {
        System.out.println("I can eat!");
    }

    public void sleep() {
        System.out.println("I can sleep!");
    }
};

// derived class
class Dog extends Animal {
 
   public void bark() {
        System.out.println("I can bark! Woof woof!!");
    }
};

// main method
void main(String[] args) {
    // Create object of the Dog class
    Dog dog1;

    // Calling members of the base class
    dog1.eat();
    dog1.sleep();

    // Calling member of the derived class
    dog1.bark();
}

Output - 
I can eat!
I can sleep!
I can bark! Woof woof!! ```

2) A call to the setTimeout() global method can block the event loop in NodeJS. Is this true or false? Why?
* That is not true. When you call setTimeout and return out of your code the server is not blocked. It is free to process other events (possibly other setTimeout callbacks) while waiting for your particular timer to fire.
* What your link Node.js How would you recreate the 'setTimeout' function without it blocking the event loop? showed was not a setTimeout blocking the event loop it was a while loop that deliberately blocks the event loop. If you want your server to be fast you do not want to block the event loop. An asynchronous callback such as setTimeout will work great.

3) How can you share information between components on a React application?
* By using props.

There are 2 cases -
* If you are using a functional component, simply catch the parentToChild in the parameters.
``` import React from 'react'

export default function Child({parentToChild}) {
    return (
        <div>
            {parentToChild}
        </div>
    )
} ```

*  If you have a class component, then just use ```this.props.parentToChild```
```import React, { Component } from 'react'

export default class Child extends Component {
    render() {
        return (
            <div>
                {this.props.parentToChild}
            </div>
        )
    }
}``` 

4) How would you protect a REST API against potential SQL Injections?
SQL Injections
* Using prepared statements will get you a lot of the way
* Consider using ORM layers to interface with your db 

Security principles
* Always validate user input before performing any operations on it
* For every operation, if you know of the universal set of options, opt for an allow-list approach vs a deny-list approach

Auth
* JWT is just a token format, and you can use oauth for the underlying auth
* Bearer tokens (like JWT) should always be sent over TLS/SSL to prevent intruders from getting access to the plaintext jwt
* As the product matures, you might want to move to a model where you start assigning session tokens that are stored on the phone, but this usually comes with the complexity of handling revocation

5) What does the level of coupling measure in software development?
* Coupling is the degree of interdependence between software modules
* A measure of how closely connected two routines or modules are
* The strength of the relationships between modules

6) What is CI? Have you used one before?
* Continuous integration (CI) is the practice of automating the integration of code changes from multiple contributors into a single software project.
* Yes, I use it lot of times.

7) How would you deploy a Node application?
* There are lot of different ways to deploy an application, but I will share using github, Heroku.
Few steps - 
* Create a 'package.json' file using the following command - ```npm init```
* Create a file called 'app.js' inside your project folder
* Create a html file 'index.html'
* Open 'app.js' file created and write few lines of code to start the server
* Open the terminal and write the following command to run the server ```node app.js```
* Now you'll see your application is running on port (whatever port you'll use)

Github - 
* Create new repository and follow instructions to put your code in github.

Heroku -
* Go to https://www.heroku.com/ and register.
* After completing the registration process, login and go to https://dashboard.heroku.com/apps
* Install Heroku CLI - ```run heroku -v```
* Login - ```heroku login```
* Create heroku app by command ```heroku create```
* Push code in cloud - ```git push heroku main```
* After push follow the instructions provided by heroku to check application deployed on server.

8) Why do we do code reviews?
* Code review helps developers learn the code base, as well as help them learn new technologies and techniques that grow their skill sets.

9) In which files would you store API tokens, passwords, or similars?
* Store your API tokens and password directly in your environment variables.
For example - yaml file is a plain-text file, it is readable by anyone who has access to the file. The file contains passwords and API tokens which need to be redacted if you want to share your configuration. By using secret you can remove any private information from your configuration files.

10) What are the benefits of using Typescript?
* The goal of TypeScript is to help catch mistakes early through a type system and to make JavaScript development more efficient.

Right now I remember few of them mentioning here - 
* Class and Module Support
* Static Type-checking
* ES6 Feature Support
* Syntax Similarity (Java)
* Superset of JavaScript

11) Describe with your own words a web socket?
* WebSocket is a communications protocol for a persistent, bi-directional, full duplex TCP connection from a user's web browser to a server.
* A WebSocket connection is initiated by sending a WebSocket handshake request from a browser's HTTP connection to a server to upgrade the connection.
For example - my live application using nodejs and web socket (https://singh-node-chat-appp.herokuapp.com/).

12) Describe with your own words a GraphQL API.
* GraphQL is designed to make APIs fast, flexible, and developer-friendly,
* A powerful data-fetching API,
* API interface that's easy to learn and work with,
* An open-source query language making APIs fast and flexible,
* A way to give experts the ability to develop APIs with desirable methods,

13) How do you keep yourself up-to-date in regards the technologies you do use? 
There are various tech websites that keep people updated with the latest technology and tech topics. I also get information with the latest technology and tech topics for example - The Verge, TechRadar, Google Cloud, Amazon Web Services, and Microsoft Azure etc.

Few more things, I want to mention here -
* Always read the latest research reports from Tech-Radar.
* Follow tech news - to get more knowledge regarding tech.
* Try to know what’s trending in the open-source community.
