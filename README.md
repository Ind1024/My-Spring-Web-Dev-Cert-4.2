# Spring-Web-Dev-Cert-4.2

## Spring Web Overview

- Basic facts about what Spring Web is, what products it consists of and how they relate to each other in terms of dependencies.


- How Spring applications can be loaded in a Servletependent of what framework is used (Spring MVC, Struts, etc.) to develop the web layer.

  https://stackoverflow.com/a/6451410
  Spring can be easily integrated into any Java-based web framework. All you need to do is to declare the ContextLoaderListener in your   web.xml and use a contextConfigLocation to set which context files to load.
  
  https://stackoverflow.com/a/27539979
  ApplicationContext and WebApplicationContext 
  
  https://stackoverflow.com/a/30259091
  the root context is loaded first and is set as the parent for the context heirarchy - the servlet context is loaded next.
  
  https://stackoverflow.com/a/18580299
  In Spring Web Applications, there are two types of container, each of which is configured and initialized differently. One is the “Application Context” and the other is the “Web Application Context”.
  
  https://stackoverflow.com/a/8458887
  To load spring in stand alone applications, Put the applicationContext in classpath, and load it in the main class
  
  https://dzone.com/articles/migrate-from-struts-to-spring-mvc-in-6-steps
  steps to migrate stucts application to use spring framework
  
  
- What is the role of the ContextLoaderListener?

https://stackoverflow.com/questions/11815339/role-purpose-of-contextloaderlistener-in-spring

- How does the application context get initialized and from what files?
#### TIP:
An easy way to explore project dependencies is to start the Spring Tool Suite, open a maven
pom.xml file for a project that uses Spring MVC, then click on the “Dependency Graph” (or the
“Dependency Hierarchy”) tab.
Alternatively, browse https://github.com/spring-projects/spring-mvc-showcase (sample applications
that highlight Spring MVC features).
SPRING MVC SERVLET CONFIGURATION
 How to configure DispatcherServlet in web.xml or using pure Java (servlet-3 style)
 Understand @EnableMvc and the WebMvcConfigurerAdapter class
 Where do the ContextLoaderListener and the DispatcherServlet can find their configuration?
 What features were introduced in Spring 4 to manage static resources?
 What is the Resource Handling Chain?
