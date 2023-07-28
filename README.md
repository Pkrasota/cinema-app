<h1 align="center">
   🎥Cinema app🎥
</h1>

<p align="center">
  <a href="#description">Description</a> •
  <a href="#features">Features</a> •
  <a href="#architecture">Architecture</a> •
  <a href="#uml-models-diagram">UML models diagram</a> •
  <a href="#technologies-used">Technologies used</a> •
  <a href="#how-to-start-the-program">How to start the program</a> 
</p>

## 📃Description
A basic RESTful application is created to manage cinema operations, encompassing essential functionalities, such as:

* User registration and authentication for future access.
* Addition and removal of movies, movie sessions, and cinema halls.
* Ability to add tickets to a shopping cart and complete the order.
* The system utilizes two main roles for authorization - `ADMIN` and `USER`
* It supports user authentication, 
authorization, and various CRUD operations (Create, Read, Update, Delete).


## 🚀Features
|  Role   | Possibility                                                                                      | Endpoints                                                                                                                                                                                                                                   |
|:-------:|:-------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `ADMIN` | Get and add movies, cinema halls<br/>Get, add and delete movie sessions<br/>Find users by email  | GET: `/cinema-halls`<br/>POST: `/cinema-halls`<br/>GET: `/movies`<br/>POST: `/movies`<br/>GET: `/movie-sessions/available`<br/>POST: `/movie-sessions`<br/>PUT: `/movie-sessions/{id}`<br/>DELETE: `/movie-sessions/{id}`<br/>GET: `/users/by-email` |
| `USER`  | Get movies, movie sessions and cinema halls<br/>Add tickets to shopping card<br/>Complete orders | GET: `/cinema-halls`<br/>GET: `/movies`<br/>GET: `/movie-sessions/available`<br/>GET: `/orders`<br/>POST: `/orders/complete`<br/>PUT: `/shopping-carts/movie-sessions`<br/>GET: `/shopping-carts/by-user`                                          |

There is also another endpoint for registering new users, which is available to everyone: `/register`
A user without an `ADMIN` role cannot perform operations, defined exclusively for users with `ADMIN` roles.

## <p id="architecture">🏗️Architecture</p>
|       3-layer architecture       |
|:--------------------------------:|
| Controllers (Presentation layer) |
|   Services (Application layer)   |
|     DAO (Data access layer)      |

## <p id="uml-models-diagram">🗺️UML models diagram</p>
![UML diagram](img/uml.png)

## <p id="technologies-used">⚙️Technologies used</p>
* JDK 11     
* Maven 4.0.0
* Apache Tomcat 9.0.50 
* Spring (WEB, Security) 5.2.2  
* Hibernate 5.4.27
* MySQL

## 🔨How to start the program
1. Clone the project from GitHub
2. Configure [`/resources/db.properties`](https://github.com/pavlogook/cinema-app/blob/main/src/main/resources/db.properties#L2) with your own URL, username, password and JDBC driver
3. Configure Tomcat server (it is recommended to use [version 9.0.50](https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.50/bin/))
4. Install Postman for sending requests
4. First user with the role of `ADMIN` will be created automatically with the following parameters: email - `admin@i.ua`, password - `admin123`
5. Run and enjoy the program 
