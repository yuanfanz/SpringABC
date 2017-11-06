### Spring In Depth

A typical Java EE architecture.
Web layer depends on Business layer and Business layer depends on Data layer.
Data layer often uses JDBC template to communicate with databases.

In Web layer, there are WebServices, Angular, Struts, MVC, Velocity, JSF, Freemarker, JSP/EL/JSTL, etc.
In Business layer, Spring.
In Data layer, JDBC, Spring Data, iBatis, Hibernate.

EXAMPLE:

```
// Web Layer
@Component
public class TodoController {
    @Autowired
    TodoBusinessService businessService;
}

// Business Layer
@Component
public class TodoBusinessService {
    @Autowired
    TodoDataService dataService;
}

// Data Layer
@Component
public class TodoDataService {
    @Autowired
    JdbcTemplate template;
}
```

