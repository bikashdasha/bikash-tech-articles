# Spring Boot REST API Guide

## Introduction
Spring Boot helps create REST APIs quickly.

## Example

```java
@RestController
public class HelloController {

@GetMapping("/hello")
public String hello(){
return "Hello World";
}

}
