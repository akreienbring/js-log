# js-log
A simple logging utility for javascript

## Why another javascript logger?
The answer is simple: Searching up and down the net I could'nt find one that fullfilled my need. 
I was looking for a logging utility that creates readable (grouped) output AND maintaines the original console context.

That means that the information where the output was logged can still be examined in the debugging console of the browser.
Sounds simple but I ended up using javascript proxies for that purpose and intercepted calls to the logger... Long story short: I had to follow a steep learning curve :-) 
Maybe this little repo speeds up the work of other javascript developers.

## What can you do with it?
Just download the js file and import it into your project: 
`import {Logger} from "./logger.js";`

Than create a create a new instance of a Logger like this:
`const logger = Logger.getNewClassLogger("App");` 

A ClassLogger is meant to be a logger for a class / module of your application.
There are also FunctionLogger which can be used to output what happens in a certain function of your class. Create one like this:
`
createThePanel(table, mode, isLoading){
  const logger = Logger.getFunctionLogger("App", "createThePanel");
`

Here's some sample output:
![sample](https://github.com/akreienbring/js-log/logger.png)

You can easily disable / enable loggers like this:
`
Logger.disable("App");
Logger.enable("App");
`
Or you choose to disable / enable all loggers:
`
Logger.disableAll();
Logger.enableAll();
`

Thats it! Happy logging!

Feb, 2020
André Kreienbring

