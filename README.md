- Spring web cert official study guide: https://d1fto35gcfffzn.cloudfront.net/academy/Spring_Web_4.2_Study_Guide.pdf

- cert notes: https://github.com/vojtechruz/spring-web-cert-notes-4.2/blob/master/Spring%20Web%20Certification%20Notes%204.2.md

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

https://stackoverflow.com/questions/6303242/loading-spring-application-context-files-that-are-inside-a-jar-in-classpath

#### TIP:
An easy way to explore project dependencies is to start the Spring Tool Suite, open a maven
pom.xml file for a project that uses Spring MVC, then click on the “Dependency Graph” (or the
“Dependency Hierarchy”) tab.
Alternatively, browse https://github.com/spring-projects/spring-mvc-showcase (sample applications
that highlight Spring MVC features).

### SPRING MVC SERVLET CONFIGURATION

- How to configure DispatcherServlet in web.xml or using pure Java (servlet-3 style)

  https://stackoverflow.com/questions/16458754/spring-web-mvc-dispatcher-servlet-xml-vs-applicationcontext-xml-plus-shared
  
  https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/WebApplicationInitializer.html
  
  https://stackoverflow.com/questions/22315672/how-to-configure-spring-mvc-with-pure-java-based-configuration

- Understand @EnableMvc and the WebMvcConfigurerAdapter class

  https://stackoverflow.com/questions/19291329/enablewebmvc-annotation-meaning
  
  http://www.logicbig.com/tutorials/spring-framework/spring-web-mvc/spring-enablewebmvc-annotation/
  
  https://docs.spring.io/spring/docs/4.1.0.RELEASE/javadoc-api/org/springframework/web/servlet/config/annotation/WebMvcConfigurerAdapter.html
  
  https://www.luckyryan.com/2013/02/07/migrate-spring-mvc-servlet-xml-to-java-config/
  
  http://www.logicbig.com/how-to/code-snippets/jcode-spring-mvc-webmvcconfigureradapter/
  
  https://dzone.com/articles/how-spring-boot-initialize-the-spring-mvc-applicat
  
  https://dzone.com/articles/spring-boot-vs-spring-mvc-vs-spring-how-do-they-compare
  
  https://dzone.com/articles/spring-mvc-and-java-based-configuration-1
  
  
- Where do the ContextLoaderListener and the DispatcherServlet can find their configuration?

- What features were introduced in Spring 4 to manage static resources?

  http://www.baeldung.com/spring-mvc-static-resources

  https://stackoverflow.com/questions/1483063/how-to-handle-static-content-in-spring-mvc
  
  https://spring.io/blog/2014/07/24/spring-framework-4-1-handling-static-web-resources
  
  https://stackoverflow.com/questions/25061237/spring-4-addresourcehandlers-not-resolving-the-static-resources

-  What is the Resource Handling Chain?

  https://spring.io/blog/2014/07/24/spring-framework-4-1-handling-static-web-resources
  
  https://www.slideshare.net/rstoya05/resource-handling-spring-framework-41
  
  https://github.com/bclozel/resource-handling-workshop/tree/master/angularjs

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


## Spring MVC Programming Model Essentials

The basics of the annotation-based programming model in Spring MVC, configuring
@Controller-annotated classes, writing request-handling methods, and testing them.

#### @REQUESTMAPPING ANNOTATION

- The purpose of the annotation, what can be annotated, and what options (or attributes) it
provides.

  https://dzone.com/articles/using-the-spring-requestmapping-annotation
  
  https://www.journaldev.com/3358/spring-requestmapping-requestparam-pathvariable-example
  
  https://static.javadoc.io/org.springframework/spring-web/4.2.0.RELEASE/index.html?org/springframework/web/bind/annotation/RequestMapping.html
  
  
- How a URL breaks down (web application context, servlet name, path info) as well as which
part of the URL is used in Spring MVC for request mapping purposes

  here servlet name is mapping to the dispatcher servlet.
  
  http://www.baeldung.com/spring-requestmapping
  
  https://stackoverflow.com/questions/13213061/springmvc-requestmapping-for-get-parameters
  
  https://stackoverflow.com/questions/2513031/multiple-spring-requestmapping-annotations
  
  http://www.logicbig.com/tutorials/spring-framework/spring-web-mvc/spring-request-mapping/

##### Tip:
In the exam you may be given basic examples of URL's and annotated controller methods. You will
be expected to predict what methods will be invoked. The best way to experiment is to try it out.
Use the course labs, and check the Spring MVC logging information on each request!
Also examine the logs for output from HandlerMapping beans. HandlerMapping beans construct
URL mappings during startup and log that information. The log level for org.springframework.web
must be set to DEBUG.

Below are a couple of specific scenarios to experiment with.
##### Scenario 1: a RequestMappingHandlerMapping with one Controller and a single method
annotated with @RequestMapping(“/foo”).
Questions: What URL's reach the method successfully? Does adding an extension to the URL
(.pdf, .xml) make a difference? How about more segments (/foo/bar)? Passing anything (/other)?

Try switching to @RequestMapping(method=RequestMethod.GET), does it still work?

##### Scenario 2: Similar to scenario 1 but involving a ControllerClassNameHandlerMapping, a
controller (FooController) and a method (bar) annotated with
@RequestMapping(method=RequestMethod.GET)

#### REQUEST HANDLING METHODS

- How to write methods to handle requests

##### TIP: Must have to read documentations/books on spring mvc

  https://stackoverflow.com/questions/17987380/combine-get-and-post-request-methods-in-spring
  
  https://doanduyhai.wordpress.com/2012/03/11/spring-mvc-part-i-request-handling/
  
  http://stacktips.com/tutorials/java/spring/how-spring-controller-request-mapping-works-in-spring-mvc
  
  https://stackoverflow.com/questions/38102569/spring-mvc-how-to-get-a-handler-method-for-a-request
  
    
- What annotations can be used?

- What the signature of the method can be – input argument types, return types?

  https://stackoverflow.com/questions/12696222/spring-mvc-controller-method-signatures
  
  https://docs.spring.io/spring/docs/3.1.x/spring-framework-reference/html/mvc.html#mvc-ann-arguments
  
  https://docs.spring.io/spring/docs/3.1.x/spring-framework-reference/html/mvc.html#mvc-ann-return-types
  
  

- What happens if the method returns void?
  
  https://stackoverflow.com/questions/8045881/can-a-controller-method-returning-void-produce-json
  
  https://stackoverflow.com/questions/12837907/what-to-return-if-spring-mvc-controller-method-doesnt-return-value
  
  https://stackoverflow.com/questions/29365833/what-are-valid-return-types-of-a-spring-mvc-controller-method
  
  https://stackoverflow.com/questions/8045881/can-a-controller-method-returning-void-produce-json
  
  https://stackoverflow.com/questions/676663/what-do-i-return-if-the-return-type-of-a-method-is-void-not-void
  
  

##### Tip:
In addition to the annotations listed below, the JavaDoc of the @RequestMapping annotation is a
good place to start for information on how input arguments and return values are interpreted on
@RequestMapping-annotated methods.

#### @REQUESTPARAM AND @PATHVARIABLE ANNOTATIONS

  ##### Differences:
  
    https://stackoverflow.com/questions/13715811/requestparam-vs-pathvariable
    
    https://javabeat.net/spring-mvc-requestparam-pathvariable/
    
    http://findnerd.com/list/view/Spring-MVC-RequestParam-vs-PathVariable/7016/
    
    https://www.dineshonjava.com/requestparam-vs-pathvariable-annotations-in-spring-mvc/
    
    https://www.journaldev.com/3358/spring-requestmapping-requestparam-pathvariable-example
    
    http://www.javapedia.net/Spring-MVC-Interview-questions/676

- The purpose of the annotation

- What can be annotated?

- What options (or attributes) does it provide?

  https://docs.spring.io/spring/docs/4.3.12.RELEASE/spring-framework-reference/htmlsingle/#portlet-ann-requestparam
  
  https://docs.spring.io/autorepo/docs/spring/4.0.4.RELEASE/javadoc-api/org/springframework/web/bind/annotation/RequestParam.html

- Can it handle optional parameters?

#### @MODELATTRIBUTE ANNOTATION

- The purpose of the annotation, what can be annotated, what options (or attributes) it
provides?

- What is the default name given to a model attribute object if the attribute name is left
unspecified?

- What is the default attribute name given to a model attribute object that is an array or a
collection?

#### OTHER ANNOTATIONS

- How do you access request headers or cookies?

- What does @Value("#{request.requestURL}") do?
August 2017 © Copyright 2017 Pivotal Software, Inc. All rights reserved 8

### Spring MVC Views

- The basics of how views work.

- What do they do?

- How are they typically instantiated through the process of view resolution?

- What is a logical view name?

- What is the default logical view name selected if a controller method does not specify it
(method returns void or null).
VIEW RESOLVERS

- The purpose of the ViewResolver strategy, and the details of configuring it?

- You should be familiar with the several different view-resolvers covered on the course.

- How do ViewResolver chains work?

- How they can be used to render multiple content types – for example to re-use the same
controller method to render HTML, PDF, or XML depending on the content type requested
by the client.

- Understanding <mvc:view-resolvers>

- Content negotiation can be specified in three different ways – how?
