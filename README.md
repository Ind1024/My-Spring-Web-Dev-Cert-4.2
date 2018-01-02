- Spring web cert official study guide: https://d1fto35gcfffzn.cloudfront.net/academy/Spring_Web_4.2_Study_Guide.pdf

- cert notes: https://github.com/vojtechruz/spring-web-cert-notes-4.2/blob/master/Spring%20Web%20Certification%20Notes%204.2.md

# Spring-Web-Dev-Cert-4.2

## Spring Web Overview

  https://dzone.com/articles/how-spring-mvc-really-works
  
  http://www.baeldung.com/category/spring-mvc/
  
  https://dzone.com/refcardz/spring-annotations

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

  https://stackoverflow.com/questions/3423262/what-is-modelattribute-in-spring-mvc
  
  ** http://www.baeldung.com/spring-mvc-and-the-modelattribute-annotation
  
  http://www.captaindebug.com/2011/11/using-spring-mvcs-modelattribute.html#.Wi3KjEqnHIU
  
  http://www.captaindebug.com/2011/11/using-spring-mvcs-modelattribute.html#.Wi3KjEqnHIU
  
  http://www.codelooru.com/2010/11/how-does-modelattribute-work.html
  
  https://javabeat.net/modelattribute-spring-mvc/
  

- What is the default name given to a model attribute object if the attribute name is left
unspecified?

  https://stackoverflow.com/questions/42462450/spring-binding-object-with-and-without-modelattribute
  
  http://www.logicbig.com/tutorials/spring-framework/spring-web-mvc/spring-model-attribute-generated-names/
  

- What is the default attribute name given to a model attribute object that is an array or a
collection?

  https://stackoverflow.com/questions/14420599/how-to-find-a-model-from-a-collection-according-to-some-attribute-other-than-the

#### OTHER ANNOTATIONS

- How do you access request headers or cookies?
  
  https://stackoverflow.com/questions/19556039/spring-mvc-controller-rest-service-needs-access-to-header-information-how-to-do
  
  https://stackoverflow.com/questions/6863443/springframework-get-all-request-headers
  
  https://stackoverflow.com/questions/28209242/read-http-headers-in-java-spring-rest-api
  
  

- What does @Value("#{request.requestURL}") do?

  https://stackoverflow.com/questions/28650149/how-exactly-works-this-rest-method-that-handle-a-post-request-in-spring
  
  https://stackoverflow.com/questions/28657056/how-exactly-does-this-rest-method-that-creates-a-new-object-work


### Spring MVC Views

  http://www.baeldung.com/spring-mvc-view-resolver-tutorial

  https://www.mkyong.com/spring-mvc/spring-mvc-internalresourceviewresolver-example/
  
  https://docs.spring.io/spring/docs/4.3.12.RELEASE/spring-framework-reference/htmlsingle/#mvc-viewresolver
  
- The basics of how views work.

- What do they do?

- How are they typically instantiated through the process of view resolution?

- What is a logical view name?

- What is the default logical view name selected if a controller method does not specify it
(method returns void or null).

#### VIEW RESOLVERS

- The purpose of the ViewResolver strategy, and the details of configuring it?

  https://www.mkyong.com/spring-mvc/configure-multiple-view-resolvers-priority-in-spring-mvc/

- You should be familiar with the several different view-resolvers covered on the course.

- How do ViewResolver chains work?

  https://dzone.com/articles/chaining-url-view-resolvers
  
  https://javabeat.net/extending-viewresolver-and-chaining-viewresolvers-in-spring-mvc/
  
  https://blog.frankel.ch/chaining-url-view-resolvers-in-spring-mvc/#gsc.tab=0
  
  https://stackoverflow.com/questions/11516494/chaining-spring-view-resolvers
  
  https://stackoverflow.com/questions/24606045/how-does-spring-know-which-view-resolver-to-use

- How they can be used to render multiple content types – for example to re-use the same
controller method to render HTML, PDF, or XML depending on the content type requested
by the client.

- Understanding <mvc:view-resolvers>

  https://stackoverflow.com/questions/18215402/spring-mvc-with-multiple-view-resolvers

  https://examples.javacodegeeks.com/enterprise-java/spring/mvc/spring-mvc-view-resolver-example/
  
  https://stackoverflow.com/questions/34698633/usage-of-different-viewresolver-in-spring-mvc
  
- Content negotiation can be specified in three different ways – how?

  https://dzone.com/articles/content-negotiation-using-0
  
  
### Spring MVC Form Processing

  https://spring.io/guides/gs/handling-form-submission/
  
  Read for spring 4.2:
  https://docs.spring.io/spring/docs/3.0.x/spring-framework-reference/html/validation.html
  
  

- The basics of working with forms such as how to configure data binding through the
@ModelAttribute annotation and how data binding is used to populate the form object from
request parameter values.

  http://www.baeldung.com/spring-mvc-form-tutorial
  
  http://www.mkyong.com/spring-mvc/spring-mvc-form-handling-example/
  
  http://websystique.com/springmvc/spring-4-mvc-form-validation-with-hibernate-jsr-validator-resource-handling-using-annotations/
  
  https://examples.javacodegeeks.com/enterprise-java/spring/mvc/spring-mvc-form-handling-example/
  
  https://dzone.com/articles/spring-mvc-example-for-user-registration-and-login-1

- Can data binding be used on a POST or can it also be done on a GET request (consider
search forms vs. forms updating data).

- How can a request handling method get access to the results of data binding?
@SESSIONATTRIBUTES ANNOTATION

  https://www.boraji.com/spring-mvc-4-sessionattributes-example
  
  https://stackoverflow.com/questions/18791645/how-to-use-session-attributes-in-spring-mvc
  
  http://www.logicbig.com/tutorials/spring-framework/spring-web-mvc/spring-model-attribute-with-session/
  
  https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/bind/annotation/SessionAttributes.html
  
  http://www.java-allandsundry.com/2014/04/using-http-session-with-spring-based.html

- The purpose of the @SessionAttributes annotation, what can be annotated, and what
options it provides.

##### Tip:

The @SessionAttributes annotation provides more than one way to specify what objects should be
added to the HTTP Session. Be sure to check them. A good way to learn what options any Spring
annotation provides is the Javadoc of the annotation.

- Understand the lifecycle of attributes specified by @SessionAttributes – how long they
remain around, when and how they can be removed from the HTTP Session.  

  https://www.intertech.com/Blog/understanding-spring-mvc-model-and-session-attributes/

  http://vmustafayev4en.blogspot.com/2012/10/power-of-springs-modelattribute-and.html
  
  https://dzone.com/articles/using-http-session-spring
  
  https://stackoverflow.com/questions/18209233/spring-mvc-how-to-remove-session-attribute
  
  http://forum.spring.io/forum/spring-projects/web/69498-when-do-sessionattributes-in-springmvc-get-removed-with-code-sample
  

- How does @SessionAttributes work when it's used with multiple controllers – for example is
the data stored globally to the HTTP session (e.g. user preferences) or is it per-controller
(e.g. account editing).

  https://coderanch.com/t/506713/framework/pass-object-MVC-controllers
  
  http://forum.spring.io/forum/spring-projects/web/114053-sessionattributes-and-two-controllers
  
  https://stackoverflow.com/questions/10401402/how-to-share-sessionattributes-between-controllers-in-spring-mvc
  
  https://www.roseindia.net/tutorial/spring/spring3/web/SessionAttributes-multiple-values.html
  
  https://coderanch.com/t/506713/framework/pass-object-MVC-controllers
    

#### @INITBINDER ANNOTATION AND DATA BINDING CUSTOMIZATIONS

- The purpose of the @InitBinder annotation, what can be annotated, and what options it
provides.

  https://dzone.com/articles/spring-initbinder-for-handling-large-list-of-java
  
  http://www.logicbig.com/tutorials/spring-framework/spring-web-mvc/spring-custom-property-editor/
  
  https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/InitBinder.html
  
  http://fruzenshtein.com/spring-mvc-validator-initbinder/
  
  http://www.logicbig.com/tutorials/spring-framework/spring-web-mvc/spring-mvc-custom-formatter/
  
  https://www.javacodegeeks.com/2013/06/spring-mvc-validator-and-initbinder.html
  
  https://www.intertech.com/Blog/spring-frameworks-webdatabinder/

- What customizations can be applied to the data binding mechanism?

   http://www.baeldung.com/spring-mvc-custom-data-binder
   
   http://www.logicbig.com/tutorials/spring-framework/spring-web-mvc/spring-request-param-data-binding/
   
   http://www.logicbig.com/tutorials/spring-framework/spring-web-mvc/spring-request-param-data-binding/
   
   https://blog.trifork.com/2011/12/08/use-immutable-objects-in-your-spring-mvc-controller-by-implementing-your-own-webargumentresolver/
   
   https://stackoverflow.com/questions/8986593/how-to-customize-parameter-names-when-binding-spring-mvc-command-objects
   
   

- What error codes are generated automatically during data binding?

- What error codes can be used to customize the errors generated during data binding?

#### SPRING FORM TAG LIBRARY

- The purpose and the value provided by the Spring form tags, and how to use them.

- How are error-messages handled? In the Controller? Using form tags?

#### FORMATTERS AND VALIDATION

- Understand the Spring stateless formatters (introduced by Spring 3.0)

- What can they do, where are they used?

- How do they interact with the formatting annotations?

- How can the form model object be validated?

- How do Spring forms leverage JSR 303 bean validation?

- How can error messages be customized?


### Spring MVC REST

  https://www.dineshonjava.com/spring-rest-web-services-interview-questions-and-answers/#22

- What does REST stand for?

- What is a resource?

- What are safe operations?

- What are idempotent operations? Why is idempotency important?

- Is REST scalable and/or interoperable?

- What are the advantages of the RestTemplate?

  http://www.tutorialsdesk.com/2016/01/spring-rest-client-with-resttemplate.html
  
  https://www.javacodegeeks.com/2014/12/spring-resttemplate-with-a-linked-resource.html
  
  https://spring.io/blog/2009/03/27/rest-in-spring-3-resttemplate

- Which HTTP-Methods does REST use?

- What is an HttpMessageConverter? How are they configured?

  http://www.baeldung.com/spring-httpmessageconverter-rest
  
  https://www.dineshonjava.com/customizing-httpmessageconverter-with-spring-mvc-in-rest/
  
  https://dzone.com/articles/customizing
  
  https://stackoverflow.com/questions/5019162/custom-httpmessageconverter-with-responsebody-to-do-json-things

- Is REST stateless?

- What does @RequestMapping do?

- Is @Controller a stereotype? Is @RestController a stereotype?

- What is the difference between @Controller and @RestControler?

  https://stackoverflow.com/questions/25242321/difference-between-spring-controller-and-restcontroller-annotation
  
  https://www.genuitec.com/spring-frameworkrestcontroller-vs-controller/
  
  https://dzone.com/articles/spring-framework-restcontroller-vs-controller
  
  https://www.dineshonjava.com/difference-between-controller-vs-restcontroller-in-spring-mvc/
  
  http://javarevisited.blogspot.com/2017/08/difference-between-restcontroller-and-controller-annotations-spring-mvc-rest.html
  
  http://javasampleapproach.com/spring-framework/spring-mvc-rest-difference-between-controller-and-restcontroller

- When do you need @ResponseBody? Or @RequestBody?

- What does @PathVariable do?

  https://stackoverflow.com/questions/19803731/spring-mvc-pathvariable
  
  https://www.boraji.com/spring-4-mvc-pathvariable-annotation-example
  
  http://www.logicbig.com/tutorials/spring-framework/spring-web-mvc/spring-path-variable/
  

- What is the HTTP status code for a delete statement? What about for a create?
  
  https://developer.mozilla.org/en-US/docs/Web/HTTP/Status
  
  http://www.baeldung.com/spring-mvc-controller-custom-http-status-code
  
  https://stackoverflow.com/questions/2342579/http-status-code-for-update-and-delete
  
  https://stackoverflow.com/questions/29545861/what-is-the-http-status-return-code-for-a-successful-delete-statement-in-rest
  
  https://developer.yahoo.com/social/rest_api_guide/http-response-codes.html

- What does CRUD mean? Which HTTP methods do you use for each CRUD operation?

  https://spring.io/understanding/REST
  
  http://www.restapitutorial.com/lessons/httpmethods.html
  

- Is REST secure? What can you do to secure it?

  https://stackoverflow.com/questions/7238094/securing-rest-api-without-reinventing-the-wheel
  
  https://restfulapi.net/security-essentials/
  
  https://www.slideshare.net/stormpath/secure-your-rest-api-the-right-way
  
  http://www.baeldung.com/securing-a-restful-web-service-with-spring-security
  
  https://dzone.com/articles/restful-api-security
  
  https://stackoverflow.com/questions/4817643/how-to-secure-restful-web-services
  
  https://softwareengineering.stackexchange.com/questions/83458/why-do-we-need-rest-service-security-if-we-have-https

- Where do you need @EnableWebMVC? What about <mvc-annotation-driven>?
  
  http://www.logicbig.com/tutorials/spring-framework/spring-web-mvc/spring-enablewebmvc-annotation/
  
  http://www.codelooru.com/2010/10/what-does-mvcannotation-driven-do.html

- Name some common HTTP response codes. When do you need @ResponseStatus?

  http://www.baeldung.com/exception-handling-for-rest-with-spring

- Does REST work with transport layer security (TLS)?

  https://www.dineshonjava.com/spring-rest-web-services-interview-questions-and-answers/#22

- Do you need Spring MVC in your classpath?

  https://www.dineshonjava.com/spring-rest-web-services-interview-questions-and-answers/#22
  
  
### Exceptions

- How can exceptions be handled in the MVC framework?

 ##### important: 
 
  https://spring.io/blog/2013/11/01/exception-handling-in-spring-mvc
 
  http://www.baeldung.com/exception-handling-for-rest-with-spring
  
  https://www.journaldev.com/2651/spring-mvc-exception-handling-controlleradvice-exceptionhandler-handlerexceptionresolver
  
  http://www.codejava.net/frameworks/spring/how-to-handle-exceptions-in-spring-mvc
  
  https://memorynotfound.com/spring-mvc-exception-handling/
  
  https://dzone.com/articles/handling-spring-mvc-exceptions
  
  https://stackoverflow.com/questions/35323174/what-are-the-advantages-of-controlleradvice-over-exceptionhandler-or-handlerex
  
  https://stackoverflow.com/questions/7228622/spring-mvc-exception-handling-with-handlerexceptionresolver?rq=1
 

- What does a ControllerAdvice class do?

- How do you set the HTTP status of a response in the event of an exception (to avoid the
default 500 error)

- Would you understand the configuration of a HandlerExceptionResolver if you saw it?

  http://www.logicbig.com/tutorials/spring-framework/spring-web-mvc/custom-handler-exception-resolver/

- What can a SimpleMappingExceptionResolver be used for?

  http://www.logicbig.com/tutorials/spring-framework/spring-web-mvc/simple-mapping-exception-resolver/
  
  http://www.logicbig.com/how-to/code-snippets/jcode-spring-mvc-simplemappingexceptionresolver/
  
  https://howtodoinjava.com/spring/spring-mvc/spring-mvc-simplemappingexceptionresolver-example/
  
  https://stackoverflow.com/questions/6343679/spring-simplemappingexceptionresolver-together-with-exceptionhandler
  

- How can a RESTful request return an error?

  https://stormpath.com/blog/spring-mvc-rest-exception-handling-best-practices-part-1
  
  https://stormpath.com/blog/spring-mvc-rest-exception-handling-best-practices-part-2
  
  http://springinpractice.com/2013/10/09/generating-json-error-object-responses-with-spring-web-mvc
  
  https://stackoverflow.com/questions/16232833/how-to-respond-with-http-400-error-in-a-spring-mvc-responsebody-method-returnin
  
  https://www.toptal.com/java/spring-boot-rest-api-error-handling
  
  
### Securing Web Applications With Spring Security

-  What web.xml configuration is required to enable Spring Security and what the mechanism Spring Security uses to protect web applications.

  http://www.baeldung.com/spring-security-login

  https://stackoverflow.com/questions/14019692/how-to-configure-spring-security-in-a-web-application
  
  https://spring.io/blog/2013/07/03/spring-security-java-config-preview-web-security/
  
  https://dzone.com/articles/securing-restful-web-service
  
  https://spring.io/guides/topicals/spring-security-architecture/
  
  https://martinfowler.com/articles/web-security-basics.html
  
  http://www.mkyong.com/tutorials/spring-security-tutorials/

-  What Spring Security related configuration is needed to secure a web application.

-  How should URL patterns be configured?

  https://stackoverflow.com/questions/24948651/spring-security-difference-between-and-url-pattern-in-spring-security
  
  https://docs.spring.io/spring-security/site/docs/current/reference/html/security-filter-chain.html
  
  http://www.baeldung.com/spring-security-multiple-entry-points
  
  https://www.kevinhooke.com/2012/03/08/configuring-spring-security-for-finer-grained-url-pattern-matching-with-a-spring-roo-app/
  
  http://www.codejava.net/frameworks/spring/spring-web-mvc-security-basic-example-part-1-with-xml-configuration
  

##### Tip:

- Pay special attention to the order in which URL patterns are provided. Does it matter if you put the
more general (e.g. /accounts/*) or the more specific (e.g. /accounts/edit) pattern first?

-  How method level security can be added to an application.

  http://websystique.com/spring-security/spring-security-4-method-security-using-preauthorize-postauthorize-secured-el/
  
  https://docs.spring.io/spring-security/site/docs/3.0.x/reference/el-access.html
  
  https://spring.io/blog/2013/07/04/spring-security-java-config-preview-method-security/
  
  http://www.baeldung.com/spring-security-expressions-basic
  
  https://howtodoinjava.com/spring/spring-security/spring-3-method-level-security-example-using-preauthorize-and-secured/
  
  https://memorynotfound.com/spring-security-method-level-annotations-example/

-  How authentication and authorization relate to each other – for example does the choice of
authentication affect authorization?

  http://www.studytrails.com/frameworks/spring/spring-security-using-db/
  
  https://dzone.com/refcardz/expression-based-authorization
  
  https://dzone.com/articles/spring-security-4-authenticate-and-authorize-users
  
  http://javawebtutor.com/articles/spring/spring-security-database-authentication.php
  
  http://www.beingjavaguys.com/2014/05/spring-security-authentication-and.html
  
  https://spring.io/guides/gs/securing-web/
  
  https://www.journaldev.com/8748/spring-security-role-based-access-authorization-example
  
 
### Testing Web Applictions

- How can the MVC layer be tested?

  https://dzone.com/articles/junit-testing-spring-mvc
  
  https://spring.io/guides/gs/testing-web/
  
  https://docs.spring.io/spring/docs/current/spring-framework-reference/testing.html
  
  https://www.slideshare.net/sbrannen/testing-spring-mvc-and-rest-web-applications

- How do we test Controller logic?

  http://www.logicbig.com/tutorials/spring-framework/spring-web-mvc/spring-mvc-unit-testing/
  
  https://stackoverflow.com/questions/34793104/what-is-the-best-way-to-test-controllers-and-services-with-junit
  
  https://infinitescript.com/2014/05/unit-testing-of-spring-mvc-controllers/

- How do we test if a Controller works properly inside the MVC framework?

- What framework artifacts/components does Spring's Mock MVC allow you to test? (Refer to
Testing Each Layer slide)

  https://www.petrikainulainen.net/spring-mvc-test-tutorial/
  
  https://docs.spring.io/spring-security/site/docs/current/reference/html/test-mockmvc.html
  
  https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/test/web/servlet/MockMvc.html
  
  https://memorynotfound.com/unit-test-spring-mvc-rest-service-junit-mockito/
  
  https://blog.zenika.com/2013/01/15/spring-mvc-test-framework/
  
  https://blog.zenika.com/2013/01/15/spring-mvc-test-framework/
  
  http://www.baeldung.com/integration-testing-in-spring
  
  https://stackoverflow.com/questions/14563489/how-to-test-a-spring-controller-method-by-using-mockmvc
  
  https://www.petrikainulainen.net/programming/spring-framework/unit-testing-of-spring-mvc-controllers-configuration/
  
  

- If presented with the code for a Mock MVC test would you understand what it is doing? – we
don't expect you to know the API from memory.


### Spring Boot:

- What is Spring Boot? What are the advantages of using Spring Boot?

  https://www.journaldev.com/7969/spring-boot-tutorial
  
  https://stackoverflow.com/questions/28831479/advantage-of-spring-boot
  
  https://spring.io/blog/2013/08/06/spring-boot-simplifying-spring-for-everyone/
  
  https://dzone.com/articles/why-springboot
  
  https://www.quora.com/What-are-the-advantages-of-Spring-Boot-over-Spring
  
  http://www.java2novice.com/java_interview_questions/spring-boot-pros-and-cons/

- Why is it “opinionated”?

- How does it work? How does it know what to configure?

- What things affect what Spring Boot sets up?

- How are properties defined? Where?

- Would you recognize common Spring Boot annotations and configuration properties if you
saw them in the exam?

- What is the difference between an embedded container and a WAR?

- What embedded containers does Spring Boot support?

- What does @EnableAutoConfiguration do? What about
@SpringBootApplication?

- What is a Spring Boot starter POM? Why is it useful?

- Spring Boot supports both Java properties and YML files. Would you recognize and
understand them if you saw them?

- Can you control logging with Spring Boot? How?

### Spring MVC and Websockets:

-  What is a web-socket?

- What is STOMP?

- How does Spring MVC support web-sockets? What annotation(s) are involved?

- How do you perform messaging with Spring MVC web-sockets?

- What is a User Destination?

- Why would you use SimpTemplate?

##### Tip:

- If you know how to use JMS or AMQP with Spring, messaging over a web-socket using SimpTemplate is similar.
