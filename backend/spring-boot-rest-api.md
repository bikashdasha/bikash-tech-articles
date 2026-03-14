# 🌱 Spring Boot REST API Guide (Complete Guide for Beginners & Developers)

## 🚀 Introduction

**Spring Boot** is one of the most powerful frameworks for building Java backend applications. It simplifies the development of REST APIs by reducing configuration and providing built-in features like dependency injection, auto-configuration, and embedded servers.

In this guide, we will learn the **important concepts of building REST APIs using Spring Boot**, including architecture, annotations, request handling, validation, and best practices.

This guide is useful for:

* 👨‍🎓 Beginners learning backend development
* 👨‍💻 Developers preparing for technical interviews
* 🧑‍🔬 Engineers building scalable REST APIs

---

# 📌 What is a REST API?

REST stands for **Representational State Transfer**.

A REST API allows different applications to communicate with each other using **HTTP requests**.

Example API endpoints:

| Method | Endpoint      | Description       |
| ------ | ------------- | ----------------- |
| GET    | `/users`      | Fetch all users   |
| GET    | `/users/{id}` | Fetch user by ID  |
| POST   | `/users`      | Create a new user |
| PUT    | `/users/{id}` | Update user       |
| DELETE | `/users/{id}` | Delete user       |

REST APIs usually send and receive **JSON data**.

Example Response:

```json
{
  "id": 1,
  "name": "Bikash",
  "role": "Developer"
}
```

---

# ⚙️ Why Use Spring Boot for REST APIs?

Spring Boot simplifies Java backend development.

### Key Advantages

* Minimal configuration
* Embedded server (Tomcat)
* Production-ready features
* Easy database integration
* Faster development

Developers can focus on **business logic instead of configuration**.

---

# 🧠 Important Spring Boot REST Annotations

Understanding annotations is essential for building REST APIs.

---

## 1️⃣ @RestController

Marks a class as a REST controller.

```java
@RestController
public class HelloController {

}
```

This annotation combines:

* `@Controller`
* `@ResponseBody`

It ensures responses are returned as **JSON or text**.

---

## 2️⃣ @GetMapping

Handles **HTTP GET requests**.

```java
@GetMapping("/hello")
public String hello() {
    return "Hello World";
}
```

API Endpoint:

```
GET /hello
```

Response:

```
Hello World
```

---

## 3️⃣ @PostMapping

Used to **create new resources**.

```java
@PostMapping("/users")
public User createUser(@RequestBody User user) {
    return userService.save(user);
}
```

---

## 4️⃣ @PutMapping

Used to **update existing data**.

```java
@PutMapping("/users/{id}")
public User updateUser(@PathVariable Long id, @RequestBody User user) {
    return userService.update(id, user);
}
```

---

## 5️⃣ @DeleteMapping

Used to **remove data**.

```java
@DeleteMapping("/users/{id}")
public String deleteUser(@PathVariable Long id) {
    userService.delete(id);
    return "User deleted successfully";
}
```

---

# 📦 Spring Boot REST API Architecture

A professional project usually follows a layered architecture.

```
Controller
Service
Repository
Model
```

---

## Controller Layer

Handles HTTP requests and responses.

```java
@RestController
@RequestMapping("/users")
public class UserController {

}
```

---

## Service Layer

Contains business logic.

```java
@Service
public class UserService {

}
```

---

## Repository Layer

Handles database operations.

```java
@Repository
public interface UserRepository extends JpaRepository<User, Long> {

}
```

---

## Model Layer

Represents database entities.

```java
@Entity
public class User {

    @Id
    private Long id;

    private String name;
}
```

---

# 🔄 REST API Request Flow

Understanding the flow of a REST API is very important.

```
Client Request
      ↓
Controller
      ↓
Service
      ↓
Repository
      ↓
Database
```

The response flows back through the same layers.

---

# 🧾 JSON Conversion

Spring Boot automatically converts Java objects to JSON using the **Jackson library**.

Example:

```java
@GetMapping("/user")
public User getUser() {
    return new User(1, "Bikash");
}
```

Response:

```json
{
  "id": 1,
  "name": "Bikash"
}
```

---

# ⚠️ Exception Handling in REST APIs

Professional applications should handle errors properly.

Example:

```java
@ControllerAdvice
public class GlobalExceptionHandler {

    @ExceptionHandler(Exception.class)
    public ResponseEntity<String> handleException(Exception ex) {
        return ResponseEntity
                .status(HttpStatus.INTERNAL_SERVER_ERROR)
                .body("Something went wrong");
    }
}
```

---

# 🔐 Validation in REST APIs

Input validation ensures that correct data is sent to the server.

Example:

```java
public class User {

    @NotNull
    private String name;

    @Email
    private String email;
}
```

Spring Boot automatically validates request data.

---

# 📊 REST API Best Practices

### 1️⃣ Use Proper HTTP Methods

| Method | Purpose         |
| ------ | --------------- |
| GET    | Retrieve data   |
| POST   | Create new data |
| PUT    | Update data     |
| DELETE | Remove data     |

---

### 2️⃣ Use Meaningful Endpoints

Good:

```
/users
/users/{id}
```

Bad:

```
/getUserData
```

---

### 3️⃣ Use Correct HTTP Status Codes

| Code | Meaning      |
| ---- | ------------ |
| 200  | Success      |
| 201  | Created      |
| 400  | Bad Request  |
| 404  | Not Found    |
| 500  | Server Error |

---

# 🧪 Testing REST APIs

You can test APIs using tools like:

* Postman
* Insomnia
* Curl

Example:

```
GET http://localhost:8080/users
```

---

# 📚 Important Concepts for Developers

Developers working with Spring Boot REST APIs should understand:

* Dependency Injection
* REST architecture
* Controller-Service-Repository pattern
* Exception handling
* Data validation
* Database integration

---

# 📈 Advanced Topics to Learn Next

After mastering the basics, explore:

* Spring Security
* JWT Authentication
* API Versioning
* Pagination
* API Documentation (Swagger)

---

# 🎯 Conclusion

Spring Boot makes it easy to develop powerful and scalable REST APIs.

By understanding the core concepts such as:

* REST principles
* Controller architecture
* HTTP methods
* Exception handling
* Validation

Developers can build **robust backend services** used in modern web applications.

Mastering these skills will help you become a **strong backend developer in the Java ecosystem**.

---

⭐ If you found this guide useful, feel free to star the repository and share it with other developers.
