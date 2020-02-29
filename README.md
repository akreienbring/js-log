# js-log
A simple logging utility for javascript

## Why another javascript logger?
The answer is simple: Searching up and down the net I couldn't find one that fullfilled my need. 
I was looking for a logging utility that creates readable (grouped) output AND maintaines the original console context.<br/><br/>

That means that the information where the output was logged can still be examined in the debugging console of the browser.
Sounds simple but I ended up using javascript proxies for that purpose and intercepted calls to the logger... Long story short: I had to follow a steep learning curve :-) <br/>
Maybe this little repo speeds up the work of other javascript developers.<br/><br/>

## What can you do with it?
Just download the js file and import it into your project:<br/> 

    import {Logger} from "./logger.js";

Than create a create a new instance of a Logger like this:<br/>

    const logger = Logger.getNewClassLogger("App");

A ClassLogger is meant to be a logger for a class / module of your application.<br/>
In contrast a FunctionLogger can be used to output what happens in a certain function of your class. Create one like this:<br/>

    createThePanel(){  
        const logger = Logger.getFunctionLogger("App", "createThePanel");

<br/>

Here's some sample output:<br/>
![sample](/screen/logger.png)

You can easily disable / enable loggers like this:<br/> 

    Logger.disable("App");  
    Logger.enable("App");

<br/>  
Or you choose to disable / enable all loggers:<br/>

    Logger.disableAll();
    Logger.enableAll();

<br/>

Finally replace all your "console.log / .error / .info / .debug / .warn" statements with their

    logger.log / .error / .info / .debug / .warn
counterparts. <br/>

Thats it! Happy logging!<br/><br/>

Feb, 2020<br/>
André Kreienbring

