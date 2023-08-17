## Spring Boot Basics

```java
// Creating a Spring Boot application
@SpringBootApplication
public class MyApplication {
  public static void main(String[] args) {
    SpringApplication.run(MyApplication.class, args);
  }
}
```

## Controllers

```java
@RestController
public class MyController {

  @GetMapping("/hello")
  public String hello() {
    return "Hello, Spring Boot!";
  }
}
```

## Dependency Injection

```java
@Service
public class MyService {
  // Service logic
}

@Controller
public class MyController {

  @Autowired
  private MyService myService;

  // Controller logic
}
```

## Data Persistence with JPA

```java
@Entity
public class Product {
  @Id
  @GeneratedValue(strategy = GenerationType.IDENTITY)
  private Long id;
  private String name;

  // Getters and setters
}

public interface ProductRepository extends JpaRepository<Product, Long> {
  // Custom queries
}
```

## REST APIs with Spring Boot

```java
@RestController
@RequestMapping("/api/products")
public class ProductController {

  @Autowired
  private ProductRepository productRepository;

  @GetMapping
  public List<Product> getAllProducts() {
    return productRepository.findAll();
  }

  @PostMapping
  public Product createProduct(@RequestBody Product product) {
    return productRepository.save(product);
  }
}
```

## Exception Handling

```java
@ControllerAdvice
public class GlobalExceptionHandler {

  @ExceptionHandler(Exception.class)
  public ResponseEntity<String> handleException(Exception e) {
    return ResponseEntity.status(HttpStatus.INTERNAL_SERVER_ERROR)
                         .body("An error occurred");
  }
}
```

## Spring Security

```java
@Configuration
@EnableWebSecurity
public class SecurityConfig extends WebSecurityConfigurerAdapter {

  @Override
  protected void configure(HttpSecurity http) throws Exception {
    http.authorizeRequests()
        .antMatchers("/admin/**").hasRole("ADMIN")
        .antMatchers("/user/**").hasRole("USER")
        .and()
        .formLogin()
        .and()
        .logout()
        .and()
        .csrf().disable();
  }
}
```

## Spring Boot Testing

```java
@SpringBootTest
class MyServiceTest {

  @Autowired
  private MyService myService;

  @Test
  void testServiceMethod() {
    // Test logic
  }
}
```

## Spring Boot Profiles

```properties
# application.properties
spring.profiles.active=dev
```

```properties
# application-dev.properties
spring.datasource.url=jdbc:mysql://localhost:3306/dev_db
```

## Spring Boot Configuration

```java
@Configuration
public class AppConfig {

  @Bean
  public MyService myService() {
    return new MyService();
  }
}
```

## Spring Boot Actuator

```properties
# application.properties
management.endpoints.web.exposure.include=*
```

## Spring Boot DevTools

```xml
<!-- pom.xml -->
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-devtools</artifactId>
  <scope>runtime</scope>
  <optional>true</optional>
</dependency>
```

>[!Note]
>This cheat-sheet provides an overview of key concepts in Java Spring Boot. For more in-depth information, refer to the official [Spring Boot documentation](https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/). If you have specific questions or need more details, feel free to ask!

#framework