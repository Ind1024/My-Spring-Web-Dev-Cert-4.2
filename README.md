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

https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/context/ContextLoaderListener.html, Java API for ContextLoaderListener

http://sunmingtao.blogspot.com/2012/10/what-does-contextloaderlistener-do-in.html : What does ContextLoaderListener do in Spring?

http://learningviacode.blogspot.com/2012/11/springs-contextloaderlistener.html: Springs' ContextLoaderListener

http://makble.com/whats-the-point-of-contextloaderlistener

http://www.codesenior.com/en/tutorial/Spring-ContextLoaderListener-And-DispatcherServlet-Concepts

https://schoudari.wordpress.com/2012/07/23/purpose-of-contextloaderlistener-spring-mvc/

- How does the application context get initialized and from what files?

https://stackoverflow.com/questions/17472954/how-to-initialize-the-application-in-spring

https://javapapers.com/spring/spring-applicationcontext/

https://spring.io/understanding/application-context

http://www.codejava.net/frameworks/spring/understanding-the-core-of-spring-framework?start=5

http://www.java2novice.com/spring/application-context-object/

https://www.tutorialspoint.com/spring/spring_applicationcontext_container.htm

https://stackoverflow.com/questions/600095/splitting-applicationcontext-to-multiple-files

#### TIP:
An easy way to explore project dependencies is to start the Spring Tool Suite, open a maven
pom.xml file for a project that uses Spring MVC, then click on the “Dependency Graph” (or the
“Dependency Hierarchy”) tab.
Alternatively, browse https://github.com/spring-projects/spring-mvc-showcase (sample applications
that highlight Spring MVC features).

### SPRING MVC SERVLET CONFIGURATION

- How to configure DispatcherServlet in web.xml or using pure Java (servlet-3 style)

- Understand @EnableMvc and the WebMvcConfigurerAdapter class

- Where do the ContextLoaderListener and the DispatcherServlet can find their configuration?

- What features were introduced in Spring 4 to manage static resources?

-  What is the Resource Handling Chain?

##### Tip:
An important concept to keep in mind is that the DispatcherServlet looks for certain types of Spring
MVC “infrastructure” beans in its Spring configuration. Examples of such types of beans include
MessageSource, HandlerMapping, ViewResolver, and others. The exam will test your
understanding of the purpose of these Spring MVC beans including what their purpose is, how they
are discovered (by bean class type or by bean id), what implementations are configured by default,
and so on.
Understanding Spring MVC “infrastructure” beans and what they do/provide is an important step to
learning Spring MVC. One way to learn is to open each type listed in the sections below, review the
class-level Javadoc, and explore available subtypes (in Eclipse/STS use the Ctrl+T shortcut to
open a class).
Another Eclipse/STS exercise is to use Ctrl+Space in Spring configuration files on bean property
names in order to see the list of available properties. These properties describe how a given
infrastructure type can be customized.

#### HANDLERMAPPING

- The purpose of the HandlerMapping strategy and the details of configuring it.

- How the RequestMappingHandlerMapping and the ControllerClassNameHandlerMapping
implementations work and what they would do in the case of specific incoming requests?

- Which is the default handler mapping?

#### HANDLERADAPTER

- The purpose of the HandlerAdapter strategy and the details of configuring it.

#### HANDLERINTERCEPTOR

- The purpose of the HandlerInterceptor strategy and the details of configuring it

- What points in the request lifecycle can be intercepted, what data is available at each point?

#### MESSAGESOURCE

- The purpose of the MessageSource strategy and the details of configuring it.

- How does Spring recognize this bean, by name or by type?

#### THE MVC NAMESPACE

- What does the mvc namespac provide, what you can configure?

- What do mvc:annotation-driven, mvc:interceptor, mvc:resource-chain and mvc:viewcontroller
actually do?

#### CONVENTION OVER CONFIGURATION

- How is Spring MVC configured by default?

- What conventions are available to reduce explicit coding?

- What features, introduced by Spring 3, must be enabled by specifying @EnableMvc or
mvc:annotation-driven?
