# Backend-Development
This project provides a REST API for user login and signup functionality using Spring Boot and JWT authentication.

Installation and Setup
Prerequisites:

-Java Development Kit (JDK) 8 or higher
-Maven or Gradle build tool
-H2 Database

Step 1: Clone the repository 

-git clone <repository_url>
-cd user-login-signup-backend

Step 2: Configure the application
Open the src/main/resources/application.properties file and modify the following properties if needed:

H2 Database settings:
spring.datasource.url=jdbc:h2:mem:userdb
spring.datasource.username=sa
spring.datasource.password=password

JWT settings:
jwt.secret=your-secret-key
jwt.expiration=86400000

Step 3: Build the application

If you are using Maven, run the following command:
-mvn clean install
If you are using Gradle, run the following command:
- gradle clean build
  
Step 4: Run the application
If you are using Maven, run the following command:
-mvn spring-boot:run
If you are using Gradle, run the following command:
-gradle bootRun
The application will start running on http://localhost:8080.

Step 5: Testing the API
You can use tools like cURL or Postman to test the API endpoints.

To signup a new user:

-Endpoint: POST http://localhost:8080/api/auth/signup
-Request body:
{
  "username": "exampleuser",
  "password": "examplepassword"
}
-Response: HTTP status 200 if successful, or 409 if the username already exists.
To login and obtain a JWT token:

-Endpoint: POST http://localhost:8080/api/auth/login
-Request body:
{
  "username": "exampleuser",
  "password": "examplepassword"
}
-Response: The JWT token as a string.
To access protected resources:

Include the JWT token in the request headers:
Authorization: Bearer <jwt_token>

Step 6: Clean up
To clean up the H2 database and reset the application, stop the application and delete the userdb.mv.db and userdb.trace.db files located in the project root directory.
