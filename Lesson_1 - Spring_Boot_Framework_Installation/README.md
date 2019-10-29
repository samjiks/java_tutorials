# Spring Boot FrameWork

- Spring Boot Framework was build on the idea of developing microservices

### Advantages of Spring Boot

* Provides a flexible way to configure Java Beans, XML configurations, and Database Transactions
* Provides a powerful batch processing and manages REST endpoints.
* Everything is autoconfigured by adding the @EnableAutoConfiguration annotation before the main class
* Offers annotation-based spring application
* Eases dependecy management
* It also includes Embedded Servlet Container

## Installation of IDE

 - I am using Intellij Idea, you could always use your favourite choice of editor
 -- Add Spring Support for IDEAJ using the configure plugin
 -- Create Spring starter from start.spring.io. Use gradle for build automation to add dependencies
 -- Add Additional Dependences, Add Lombok, Web for Restful services

## Looking at the project

* Spring Boot Main Class contains the entry point of the application. which is @SpringBootApplication
  @ComponentScan - scan all the beans and package declaration in the project

* SpringBootApplication includes all others annotation in @EnableAutoConfiguration, @ComponentScan and @SpringBootConfiguration 

* Spring Boot Starters which are added in depenedcies in gradle(build.gradle) or maven files(pom.xml)

  - spring-boot-starter-data-jpa - Spring and JPA for database access
  - spring-boot-starter-actuator - Monitor and manage your applications checking your health endpoint
  - spring-boot-starter-web - Write a Rest Endpoints.
  - spring-boot-starter-security
  - spring-boot-starter-test - Writing Test case

'''
package com.samjiks.product;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class ProductServiceApplication {

	public static void main(String[] args) {
		SpringApplication.run(ProductServiceApplication.class, args);
	}

}
'''



