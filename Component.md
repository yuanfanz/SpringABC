### Component Scan for beans

@SpringBootApplication annotation will automatically scan the project and find components for running.
But when we do not have this annotation, we need @ComponentScan to determine and pick up the components.

@ComponentScan("com.spring.xxx.component")
This will include the com.spring.xxx.component package into the project.




