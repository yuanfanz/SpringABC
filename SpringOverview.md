### Spring Framework Overview
- Tight coupling & Loose coupling

- Create beans and wiring
  
  What are the beans: @Component annotation will tell Spring framework they are beans.
  
  What are the dependencies of a bean: @Autowired annotation will tell Spring framework it's a dependency.
  
  Where to search for beans: @SpringBootApplication annotation automatically scans the package. And search beans in this package.

- Spring application context manage beans.
  
  SpringApplication.run(project.class, args);
  
  ApplicationContext.getBean(method.class);
- logging.level.org.springframework = debug
  
  Find how is Spring framework is worked in the background including autowiring, manage dependencies and create beans.
  
  Spring will only request one bean at one time. Or we can use @Primary annotation to give importance between different beans.
  
  If there is not any beans, errors will show we cannot execute getBean() method. So make sure we have @Component put in the class.
- Setter injection & Constructor injection

### Spring Modules
- Core Container
  Beans, Core, Context, SpEL
- Data Access/Integration
  JDBC, ORM, OXM, JMS, Transactions
- Web
  WebSocket, Servlet, Web, Portlet
- Test
- AOP, Aspects, Instrumentation, Messaging

### Spring projects
- Spring Boot: Quickly build applications
- Spring Cloud: Build cloud native apps
- Spring Data: Consistent data access
- Spring Integration: Application integration
- Spring Batch: Batch applications
- Spring Security: Protect applications
- Spring HATEOAS: HATEOAS compatible services
- Others: Spring web services, Spring sessions

### Spring advantages
- Enables testable code
- No plumbing code
- Flexible architexture, very modular
- Staying relevant, keep in the trend
