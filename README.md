# Table
1. [Spring Boot Main Annotations](#spring-boot-main-annotations)
   - [**@SpringBootApplication**](#springbootapplication)
   - [**@ComponentScan**](#componentscan)
   - [**@EnableAutoConfiguration**](#enableautoconfiguration)
   - [**@Configuration**](#configuration)

2. [Stereotype Annotations](#stereotype-annotations)
   - [**@Component**](#component)
   - [**@Service**](#service)
   - [**@RestController / @Controller**](#restcontroller--controller)
   - [**@Repository**](#repository)

3. [Spring Core Related Annotations](#spring-core-related-annotations)
   - [**@Configuration**](#configuration-1)
   - [**@Bean**](#bean)
   - [**@Autowired**](#autowired)
   - [**@Qualifier**](#qualifier)
   - [**@Lazy**](#lazy)
   - [**@Value**](#value)
   - [**@PropertySource**](#propertysource)
   - [**@ConfigurationProperties**](#configurationproperties)
   - [**@Profile**](#profile)
   - [**@Scope**](#scope)

4. [REST API Related Annotations](#rest-api-related-annotations)
   - [**@RestController**](#restcontroller-1)
   - [**@RequestMapping**](#requestmapping)
   - [**@GetMapping, @PostMapping, @PutMapping, @DeleteMapping**](#getmapping-postmapping-putmapping-deletemapping)
   - [**@RequestBody**](#requestbody)
   - [**@PathVariable**](#pathvariable)
   - [**@RequestParam**](#requestparam)
   - [**@ControllerAdvice & @ExceptionHandler**](#controlleradvice--exceptionhandler)

5. [Spring Data JPA Related Annotations](#spring-data-jpa-related-annotations)
   - [**@Entity**](#entity)
   - [**@Table**](#table)
   - [**@Column**](#column)
   - [**@Transactional**](#transactional)
   - [**@OneToOne, @OneToMany, @ManyToOne, @ManyToMany**](#onetoone--onetomany--manytoone--manytomany)

6. [Caching Related Annotations](#caching-related-annotations)
   - [**@Cacheable**](#cacheable)
   - [**@CachePut**](#cacheput)
   - [**@CacheEvict**](#cacheevict)
   - [**@CacheConfig**](#cacheconfig)
   - [**@EnableCaching**](#enablecaching)
  
7. [Thread Related Annotations](#thread-related-annotations)
   - [**@Async**](#async)
   - [**@Scheduled**](#scheduled)
   - [**@EnableAsync**](#enableAsync)
   - [**@EnableScheduling**](#enablescheduling)
   - [**@ThreadScope**](#threadscope)

---

## Spring Boot Main Annotations:
### @SpringBootApplication:
- This annotation is a combination of `@Configuration`, `@EnableAutoConfiguration`, and `@ComponentScan`.
- It marks the main class of a Spring Boot application, providing configuration, enabling auto-configuration, and specifying the base package for component scanning.

### @ComponentScan:
- Scans the specified package for Spring components (like beans, controllers, services) and registers them in the application context.
- It can be used at the class level to specify the base package for scanning.

### @EnableAutoConfiguration:
- Enables Spring Boot's automatic configuration based on the project's dependencies.
- It attempts to guess and configure beans based on the classpath.

### @Configuration:
- Indicates that a class declares one or more `@Bean` methods and may be processed by the Spring container to generate bean definitions and service requests for those beans.

# Stereotype Annotations:
### @Component:
- Indicates that a class is a Spring component.
- Such classes are automatically detected and registered as beans during component scanning.

### @Service:
- Specialized version of `@Component` used to indicate that a class is a service.

### @RestController / @Controller:
- Marks a class as a controller in Spring MVC.
- `@RestController` is a specialized version of `@Controller` that combines `@Controller` and `@ResponseBody`.

### @Repository:
- Indicates that a class is a repository, typically used for database access.
- It is a specialization of `@Component`.

## Spring Core Related Annotations:
### @Configuration:
- Indicates that a class declares one or more `@Bean` methods and may be processed by the Spring container to generate bean definitions and service requests for those beans.

### @Bean:
- Indicates that a method produces a bean to be managed by the Spring container.
- It is used in conjunction with `@Configuration`.

### @Autowired:
- Marks a constructor, field, method, or parameter to be autowired by Spring's dependency injection facilities.

### @Qualifier:
- Used in conjunction with `@Autowired` to specify the name of the bean to be injected when there are multiple candidates.

### @Lazy:
- Delays the initialization of a bean until it is first requested.

### @Value:
- Injects values into fields in a Spring bean.

### @PropertySource:
- Declares a property source to be added to the Environment's set of property sources.

### @ConfigurationProperties:
- Binds and validates external configuration properties to a class.

### @Profile:
- Specifies which beans should be registered based on the active profiles.

### @Scope:
- Defines the scope of a bean (e.g., singleton, prototype).

## REST API Related Annotations:
### @RestController:
- A specialized version of `@Controller` that is a convenient annotation for creating RESTful controllers.

### @RequestMapping:
- Maps HTTP requests to handler methods.

### @GetMapping, @PostMapping, @PutMapping, @DeleteMapping:
- Shortcut annotations for `@RequestMapping(method = RequestMethod.GET/POST/PUT/DELETE)`.

### @RequestBody:
- Indicates that a method parameter should be bound to the body of the web request.

### @PathVariable:
- Extracts values from the URI template and binds them to method parameters.

### @RequestParam:
- Binds a web request parameter to a method parameter.

### @ControllerAdvice & @ExceptionHandler:
- Used together to define global exception handlers for controllers.

## Spring Data JPA Related Annotations:
### @Entity:
- Marks a class as a JPA entity.

### @Table:
- Specifies the primary table for the annotated entity.

### @Column:
- Used to define the properties of the column in a database table.

### @Transactional:
- Defines the scope of a single database transaction.

### @OneToOne, @OneToMany, @ManyToOne, @ManyToMany:
- Define the relationships between entities in JPA.

## Caching Related Annotations:
### @Cacheable:
- Indicates that the result of a method should be cached.

### @CachePut:
- Updates the cache with the result of the method execution.

### @CacheEvict:
- Evicts one or more entries from the cache.

### @CacheConfig:
- Shares some common cache-related settings at the class level.

### @EnableCaching:
- Enables Spring's annotation-driven cache management.


Here is the threading related Spring annotations summary in Markdown format for a README.md:

## Threading Related Annotations

### @Async:

- Indicates that a method should be executed asynchronously, allowing the calling method to continue its execution without waiting for the completion of the annotated method. 

- Example:

```java
@Async 
public Future<String> asyncMethod() {
  // Asynchronous method implementation
}
```

### @Scheduled:

- Used to schedule the execution of a method at fixed intervals or using cron expressions.

- Example: 

```java 
@Scheduled(fixedRate = 5000)
public void scheduledMethod() {
  // Scheduled method implementation
}
```

### @EnableAsync:

- Enables Spring's asynchronous method execution capability.

- It is typically used at the configuration class level.

- Example:

```java
@Configuration
@EnableAsync  
public class AppConfig {
  // Configuration code
}
```

### @EnableScheduling:

- Enables Spring's scheduled task execution capability.

- It is typically used at the configuration class level. 

- Example:

```java
@Configuration
@EnableScheduling
public class AppConfig {
  // Configuration code  
}
```

### @ThreadScope:

- Defines a custom thread scope for a bean, allowing the bean to be bound to a thread.

- Useful when different threads require their own instances of a bean.

- Example:

```java
@Component
@ThreadScope 
public class ThreadScopedBean {
  // Thread-scoped bean implementation
}
```
