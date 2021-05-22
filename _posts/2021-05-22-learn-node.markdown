---
layout: post
title:  "Learn Node"
date:   2021-05-22 17:04:00 +0530
categories: node nodejs backend
---
Node is a javascript runtime based on `Google Chrome V8 Engine`

{% highlight javascript %}
modue.exports = name
{% endhighlight %}

above code snippet is used to export an entity delcared in a module

npm is the package manager for node modules. `npm init` is used to initialize the node project which bascially creates the configuration file package.json. So when we install any module using npm, it will automatically added to package.json file

`chalk` is node module for color coded loggin
`validator` is a node module for many string validations


### Nodejs event Loop
Nodejs event loop is single threaded , which interacts with a pool of background C++ threads for IO operations
* Event Queue
Tasks that are declared in program or callbacks after completion of background tasks
* Event Loop
It is the main Node.js thread that faciliates event queues and worker thread pools to carry out operations both async and synchronous.
* BreakGround Thread Pool
These threads do the acutal processing of IO tasks (async tasks)

![Nodejs exceution model](/assets/images/processing-model.png)
Diagram courtesy of c-sharpcorner.com

Reference [Freecodecamp blog][freecodecamp-nodejs-async] 

#### Problems with callback
1. Callback hell
We will have nested callbacks which indent towards right. 
Solution is to use proper functions instead of nested callbacks
2. Inversion of control
We don't know how higher order functions executed the callback that they got as part of function parameters (they can execute first or execute last or execute multiple times)

As a best practise
* Stick to the conventional callback signature with error as the first argument
* Execute a callback only once at the end of your higher-order function
* Document anything out-of-convention that is absolutely required and always aim for backward compatibility

Recommend solution is to use `Promise`. One limitation with promise is that, we can access data return from previous promise in chain because of memory sharing issue between c++ threads. This is solve using `Promise.all[]`

We can also use `Async/Await` when we want to execute set of instuctions sequentially (i.e data from previous step is used by current step)

[freecodecamp-nodejs-async]: https://www.freecodecamp.org/news/