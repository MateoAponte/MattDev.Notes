---
Creation date: 2024-09-01 20:45
Modification date: domingo 1º septiembre 2024 20:45:39
Topic: Some Topic
Difficulty:
  - High
  - Medium
  - Lower
---

---

**Tags:** #Develop #Develop/BFF/NestJS  
**Links:** 
* [Fazt Code Curse](https://www.youtube.com/watch?v=wsqcg5ZtUMM)

---

# What is?
Is a Open Source progressive Framework for NodeJS, that use TS to create scalable app's
Mix concepts of POO, Reactive programming and Functional programming

The Scaffold organization are inspired by Angular.

NestJS have the unique particularity that works with modules and commands
![[Pasted image 20240901222244.png]]

The Commands are a important feature about *NestJS* cause prevents the repetitive tasks and summary this in fastly executions

# Foundations

## Modules
When we talk about modules, is related to one principal feature and will allowed all the Module configuration, such Controllers, , etc and this modules can be Tasks, Auth, Shopping, etc.

**Command:**
````js
nest g mo [ModuleName]
````

---
## Controllers
Are functions and logic that are executed when a module is called, have the particularity that the Controller decorator determine the principal route name and each function the neste route
````js
nest g co [ControllerName]

// To create without test
nest g co [ControllerName] --no-spec
````

![[Pasted image 20240901224211.png]]
In this case the route is /tasks/get-task to return all 


---
## Service
Are reusable functions into the project, that will used in whatever place. This is done 'cause the App *Injects* and *Provide* a serie of functions, or in this case **Services** that can be used easy.

````js
nest g s [ServiceName]

// To create without test
nest g s [ServiceName] --no-spec
````

![[Pasted image 20240901225150.png]]
The *injectable* do that the Service will be **injected** in the *modules* 


![[Pasted image 20240901225230.png]]

The *module* provided all the tasks



| Way #1                               | Way #2                               |
| ------------------------------------ | ------------------------------------ |
| ![[Pasted image 20240901225535.png]] | ![[Pasted image 20240901225537.png]] |
And the *Controller Constructor* will **inject** the service in the app

## HTTP Methods
### Methods
Using decorators you can use all the **HttpMethods** and define with the same route the App Behaviour
![[Pasted image 20240901230150.png]]

### Status
By Decorators can return other *Status Code* by the requirement, using **@HttpCode**
![[Pasted image 20240902105248.png]]
![[Pasted image 20240902105623.png]]

## Request, Response and Express API
![[Pasted image 20240902093313.png]]
The *Req* and *Res* is the same of  Express Api, so all the configs and options are the Same

### Querys
Returns an Object with Any element
![[Pasted image 20240902094627.png]]

### Params
Return a String by each Param
![[Pasted image 20240902094614.png]]

## DTO - Data Object Transform
The DTO are Interfaces to Each Method and describe the behaviour of the *Objects*

````js
dto/create-task.dto.ts
````


## Class-Validator and Pipes
Each dto or class on Nest have the possibility of check the data types of the attributes by some Decorators

### Class Validators
The class validator are Decorators that enable the type check of each Class
![[Pasted image 20240902101609.png]]

### Pipes
The Pipes are a decorator that forces to the method check the data type and context type
![[Pasted image 20240902101625.png]]

In this idea order when i send a *request* that no supplies the class requirements the request *will* failed with the current error

![[Pasted image 20240902101830.png]]


The Framework return some Pipes, to do validations into *Params* or *Querys*
````js
@Param('num', ParseIntPipe)
@Param('active', ParseBoolPipe)
````

In this way you can create your Custom Pipes

````js
nest g pi [ControllerName]/pipes/[MethodMame]Pipe

// To create without test
nest g pi [ControllerName]/pipes/[MethodMame]Pipe --no-spec
````

![[Pasted image 20240902110841.png]]
In this way validate and return errors depending of the checks

## Guards
Are functions control the access to functions depending of the code logic, this is so useful to check Auth process.

![[Pasted image 20240902142516.png]]

In this way you can create your Custom Pipes

````js
nest g gu [ControllerName]/guards/[PurposeName]Guard

// To create without test
nest g gu [ControllerName]/guards/[PurposeName]Guard --no-spec
````


# Advanced Features
## Global Configs
NestJS enable the possibility of config all the Controllers to use *Pipes*, *Guards*, *Interceptors* or *Filters* depending of the necessity.
![[Pasted image 20240902104957.png]]

In this case is config Global Pipes but only execute the pipe in the Controller that is called this function

## Middleware
Function that is executed between two functions, this with the purpose of provide a unified service between techs. Can use the *Express API* to parsed the *Req* and *Res*

![[Pasted image 20240902144205.png]]

But, to config, and enable access to this middleware for all the Route, need to modify the *main module*


| For Module                           | For Route                            |
| ------------------------------------ | ------------------------------------ |
| ![[Pasted image 20240902144348.png]] | ![[Pasted image 20240902144524.png]] |

## Resources
Is the way to the fast generation code in NestJS, before we create one by one each file, with the resources can create all a package of resources depending of the necessity

````js
nest g res [ResourceName]
````


## Database
To connect a BD with Nest, they provide a code so specific that allow connections to all the BD's and to be more easy this process, Nest have a **ORM** integrated

All connections
https://docs.nestjs.com/techniques/database
## Swagger
Is a generator that provides all the API detailed description, using a NestJS module to do this work more easy.

Go to: [[Swagger]]

# Usage Tips
-

# Best Practices
-

# Bad Practices
-

# Roadmap
-

---