### Spring AOP

Provided by default by Spring framework, not as powerful as aspectj. A very popular application in Spring framework.
AOP is the best approach for cross cutting platform. 

Annotation: @Service

```
@Service
public class Dao1 {
    
    public String retrieveSomeData() {
        return "Dao1"
    }
    
}
```

```
@Service
public class BUsiness1 {
    @Autowired
    private Dao1 dao1;
    
    public String calculate() {
        Dao1.retrieveSomeData();
    }
}
```

