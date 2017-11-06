### Autowiring

1. Use name at instance to specify the implementation.
2. Use @Primary annotation to specify.

And @Primary annotation has higher priority than naming.

3. The third option to use @Autowired when you have multiple candidates for it.
We can use @Qualifier("quick") annotation to specify the implementation we want.
In this case, we use quick sort when we enter quick in the annotation.

@Primary annotation is the most efficient way to use if we have choices.
Use autowiring by name is also recommended cause it is very clear.

### Bean Scope

- default: singleton, one instance per Spring Context.
- prototype: new bean whenever requested.
- request: One bean per HTTP request.
- session: One bean per HTTP session.

@Scope("prototype") annotation will give you new beans whenever requested.

And this annotation better written as follow:
@Scope(ConfigurableBeanFactory.SCOPE_PROTOTYPE)
@Scope(ConfigurableBeanFactory.SCOPE_SINGLETON)

If we don't use any annotations, default is Singleton. If we use @Scope annotation, we can specify prototype beans.

And we can use different types of beans in for example, JDBC connection and personDAO.
We can use different types of beans as we like under different circumstances.

- @Scope(value=ConfigurableBeanFactory.SCOPE_PROTOTYPE, proxyMode = ScopedProxyMode.TARGET_CLASS)
We need to use proxy to make sure we get a bean each time when using JDBC if we put this annotation above JDBC connection.


```java
@Component
public class PersonDAO {
    @Autowired
    JdbcConnection jdbcConnection;
    
    public JdbcConnection getJdbcConnection() {
        return jdbcConnection;
    }
    public JdbcConnection setJdbcConnection(JdbcConnection jdbcConnection) {
        this.jdbcConnection = jdbcConnection;
    }
}

@Component
public class JdbcConnection {
    public jdbcConnection() {
        System.out.println("JDBC Connection");
    }
}

public class ScopeApplication {
    
    private static Logger LOGGER = LoggerFactory.getLogger(ScopeApplication.class);
    
    public static void main(String[] args) {
        
        ApplicationContext applicationContext = SpringApplication.run(ScopeApplication.class, args);
        
        PersonDAO personDAO = applicationContext.getBean(PersonDAO.class);
        
        PersonDAO personDAO1 = applicationContext.getBean(PersonDAO.class);     
        
        LOGGER.info("{}", personDAO);
        LOGGER.info("{}", personDAO.getJdbcConnection());
        
        LOGGER.info("{}", personDAO1);
        LOGGER.info("{}", personDAO.getJdbcConnection());
    }
}
```