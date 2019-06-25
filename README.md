# Building-a-RESTful-Web-Service
Building a RESTful Web Service

Basic WS - REst + WEb
1. 
@RestController annotation, which marks the class as a controller where every method returns a domain object instead of a view. It’s shorthand for @Controller and @ResponseBody rolled together.

2. 
@RequestParam binds the value of the query string parameter name into the name parameter of the greeting() method. If the name parameter is absent in the request, the defaultValue of "World" is used.

    @RequestMapping("/greeting")
    public Greeting greeting(@RequestParam(value="name", defaultValue="World") String name) {
        return new Greeting(counter.incrementAndGet(),
                            String.format(template, name));
    }
    
 3. 
 @SpringBootApplication is a convenience annotation that adds all of the following:

    @Configuration tags the class as a source of bean definitions for the application context.

    @EnableAutoConfiguration tells Spring Boot to start adding beans based on classpath settings, other beans, and various property settings.

Normally you would add @EnableWebMvc for a Spring MVC app, but Spring Boot adds it automatically when it sees spring-webmvc on the classpath. This flags the application as a web application and activates key behaviors such as setting up a DispatcherServlet.

    @ComponentScan tells Spring to look for other components, configurations, and services in the hello package, allowing it to find the controllers.
