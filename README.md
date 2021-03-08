# MASTER MICROSERVICES WITH SPRING BOOT AND SPRING CLOUD

## Restful Web Services w/Spring Boot
* Software system designed to support interoperable (not platform dependent), machine-to-machine interaction over a network (means of communication)
* Input to a web service is a REQUEST, output is a RESPONSE
* 2 popular (data exchange formats for REQUEST/RESPONSE:
  * XML: extensible markup language (open/closed nodes)
  * JSON: JavaScript Object Notation (curly brackets)
* Service definition:
  * specifies req/res format and endpoint (location)
  * contract between the service provider and the service consumer
* Web Service, aka Service Provider (Server) is the one hosting the web service
* Service Consumer (Client) consumes the service from the web service, ex: Java App, .Net App, etc
* Transport: defines how a service is called
  * HTTP: over the web, typing a url
  * MQ: communication over a queue
* 2 diff types of web services: SOAP & REST
  * both are not comparable
* SOAP
  * simple object access protocol, request/response
  * defines a specific way of building web services
  * uses XML req/res format
  * transports over MQ or HTTP
  * service definition is Web Service Definition Language
  * must have envelope with header (meta info) and body (content)
* REST
  * Representational State Transfer
  * http request methods - GET, POST, PUT, PATCH, DELETE
  * Resource has a URI (location)
  * format has no restrictions although, JSON is popular
  * transport is only HTTP (hyper text transfer protocol)
  * service definition: no standard, WADL, Swagger
* Set up project using Spring Initializer
  * [initializer link](start.spring.io)
  * generate ```maven project``` (build tool to be used)
  * with ```Java```
  * use spring boot version greater than v2.0.0
  * group: com.in28minutes.rest.webservices
  * artifact: restful-web-services
  * dependencies
    * web (starter for web services/web apps)
    * DevTools (makes easy to develop web apps)
    * JPA (Java Persistence API)
    * H2 (embedded database)
  * generate project
    * generates maven project in zip and downloads
    * unzip to some folder
    * launch editor
    * import existing maven project (file to import maven, existing maven projects)
    * browse to where you unzipped
 * REST is a style of software architecture
 * When a RESTful API is called, the server will transfer to the client a representation of the state of the requested resource
 * HTTP verbs:
    * Retrieve all Users: GET /users
    * Create a User: POST /users
    * Retrieve one User: GET /users/{id}
    * Delete a User: DELETE /users/{id}
 * User -> Posts (One to many relationship)
    * Retrieve all posts for a Yser: GET /users/{id}/posts
    * Create posts for a User: POST /users/{id}/posts
    * Retrieve details of a post: GET /users/{id}/posts/{post_id}
 * Hello World Controller
    * [Java Repl Code Link](https://repl.it/@9derick/FavorableMinorQuadrant#HelloWorldBean.java)
 * Returning a Bean
    * see above repl
    * make a new Java object and return it (the HelloWorldBean)
    * put cursor on the end of the line for the new Java object, right click and make a new class
    * right click on the string of hello world in the controller and create a constructor (pay attention to compiler errors)
    * change hello world to a String message
    * create getters and setters for message
    * generators are under the code tab at the top of the editor
 * dispatcher servlet: Go to application.properties, check debug logs, check auto configuration log
 * spring boot auto configuration is configuring the dispatcher servlet and configuring the error mapping
 * dispatcher servlet handles all the requests and follows the pattern of front controller
 * URL typed in browser, GET request is made, dispatcher servlet looks for right controller to execute, response body annotation allows response to be mapped by message converter to some format (we're using jackson message converter in this tutorial), conversion envoked, converted into JSON, response returned back
 * path variable can be string interpolated (ex: path-variable/{name})
 * ```public HelloWorldBean helloWorldBean(@PathVariable String name)```
 * string template: ```String.format("Hello World, %s", name)```
 * pather variables are important for REST resources
 * User class created(aka user bean)
    * give 3 variables: id, name, birthdate
    * import java util for date
    * generate getters/setters/toString/constructor for all variables
    * user dao will be created to manage user; it talks to the database to get details
    * static array used with this dao
    * create helloworld package with bean/controller
    * create user package with user in it
    * appending @Component before the class name ensures it's managed by Spring
    * create simple list of users, static list
    * create findAll method which returns list of all users
    * create saveUser which saves user to database
    * create findOne to find single user
    * create a new user resource class in the user package

## Intro to Microservices
**Notes here**

## Microservices with Spring Cloud - V1

## Microservices with Spring Cloud - V2

## Docker with Microservices using Spring Boot and Spring Cloud - V2

## Kubernetes with Microservices using Docker, Spring Boot and Spring Cloud - V2
