# 

# Deploying a module into AlvisNLP

This document present meterials to integrate new modules into the Alvis engine. It is designed for application developers. The special skills required to better understand the contents of these guidelines are the Java, maven environment, and the XML language.

In the Alvis engine, the modules are detached from the core engine that manage their execution. A developer can thus add new modules to the Alvis engine, create access interfaces for the modules, and let users make use of their functionalities. 

In the following, different materials required are provided in order to deploy, integrate and run a module into the AlvisNLP engine.

1. [the module elements and conventions for to create a module](/alvis-module-elements-and-conventions.md): this part presents meterials needed to implement a module into Alvis. The tasks implied here are done by Java developers.
2. [the module is recognized and integrated into the AlvisNLP system](alvis-module-recognition-and-integration.md): this part, shows how a implemented module is recognized, compiled and integrated into the Alvis System. All required is by default present into the Alvis system for this step to be done automatically.
3. [the module into the system is loaded and executed](alvis-module-access-loading-and-execution.md) : this part presents the module execution. It also concerns the interface acces for the module. 

Note:- point 1. presents the infrmation required to implement and make a module compatible with Alvis. Point 2. gives some justifications about why the point 1. is required by showing how alvis explode the well-defined modules. Point 3. gives information about the real use of the module, its access, invocation by users, and execution process.





