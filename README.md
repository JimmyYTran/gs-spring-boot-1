# Spring Boot Getting Started Guide

This guide provides a sampling of how {spring-boot}[Spring Boot] helps you accelerate and facilitate application development. As you read more Spring Getting Started guides, you will see more use cases for Spring Boot.

It is meant to give you a quick taste of Spring Boot. If you want to create your own Spring Boot-based project, visit

[Spring Initializr](http://start.spring.io/), fill in your project details, pick your options, and you can download either
a Maven build file, or a bundled up project as a zip file.

#### What you'll build
You'll build a simple web application with Spring Boot and add some useful services to it.

#### What you'll need

* java_version: 11

#### Learn what you can do with Spring Boot

Spring Boot offers a fast way to build applications. It looks at your classpath and at beans you have configured, makes reasonable assumptions about what you're missing, and adds it. With Spring Boot you can focus more on business features and less on infrastructure.

For example:

* Got Spring MVC? There are several specific beans you almost always need, and Spring Boot adds them automatically. A Spring MVC app also needs a servlet container, so Spring Boot automatically configures embedded Tomcat.
* Got Jetty? If so, you probably do NOT want Tomcat, but instead embedded Jetty. Spring Boot handles that for you.
* Got Thymeleaf? There are a few beans that must always be added to your application context; Spring Boot adds them for you.

These are just a few examples of the automatic configuration Spring Boot provides. At the same time, Spring Boot doesn't get in your way. For example, if Thymeleaf is on your path, Spring Boot adds a `SpringTemplateEngine` to your application context automatically. But if you define your own `SpringTemplateEngine` with your own settings, then Spring Boot won't add one. This leaves you in control with little effort on your part.

NOTE: Spring Boot doesn't generate code or make edits to your files. Instead, when you start up your application, Spring Boot dynamically wires up beans and settings and applies them to your application context.

#### Create a simple web application
Now you can create a web controller for a simple web application.

`src/main/java/hello/HelloController.java`

The class is flagged as a `@RestController`, meaning it's ready for use by Spring MVC to handle web requests. `@RequestMapping` maps `/` to the `index()` method. When invoked from a browser or using curl on the command line, the method returns pure text. That's because `@RestController` combines `@Controller` and `@ResponseBody`, two annotations that results in web requests returning data rather than a view.

#### Create an Application class
Here you create an `Application` class with the components:

`src/main/java/hello/Application.java`

There is also a `CommandLineRunner` method marked as a `@Bean` and this runs on start up. It retrieves all the beans that were created either by your app or were automatically added thanks to Spring Boot. It sorts them and prints them out.

#### Run the application
To run the application, execute:

Let's inspect the beans provided by Spring Boot:
* application
* beanNameHandlerMapping
* defaultServletHandlerMapping
* dispatcherServlet
* embeddedServletContainerCustomizerBeanPostProcessor
* handlerExceptionResolver
* helloController
* httpRequestHandlerAdapter
* messageSource
* mvcContentNegotiationManager
* mvcConversionService
* mvcValidator
* org.springframework.boot.autoconfigure.MessageSourceAutoConfiguration
* org.springframework.boot.autoconfigure.PropertyPlaceholderAutoConfiguration
* org.springframework.boot.autoconfigure.web.EmbeddedServletContainerAutoConfiguration
* org.springframework.boot.autoconfigure.web.EmbeddedServletContainerAutoConfiguration$DispatcherServletConfiguration
* org.springframework.boot.autoconfigure.web.EmbeddedServletContainerAutoConfiguration$EmbeddedTomcat
* org.springframework.boot.autoconfigure.web.ServerPropertiesAutoConfiguration
* org.springframework.boot.context.embedded.properties.ServerProperties
* org.springframework.context.annotation.ConfigurationClassPostProcessor.enhancedConfigurationProcessor
* org.springframework.context.annotation.ConfigurationClassPostProcessor.importAwareProcessor
* org.springframework.context.annotation.internalAutowiredAnnotationProcessor
* org.springframework.context.annotation.internalCommonAnnotationProcessor
* org.springframework.context.annotation.internalConfigurationAnnotationProcessor
* org.springframework.context.annotation.internalRequiredAnnotationProcessor
* org.springframework.web.servlet.config.annotation.DelegatingWebMvcConfiguration
* propertySourcesBinder
* propertySourcesPlaceholderConfigurer
* requestMappingHandlerAdapter
* requestMappingHandlerMapping
* resourceHandlerMapping
* simpleControllerHandlerAdapter
* tomcatEmbeddedServletContainerFactory
* viewControllerHandlerMapping

You can clearly see `org.springframework.boot.autoconfigure` beans. There is also a `tomcatEmbeddedServletContainerFactory`.

Check out the service from a web browser:

`http://localhost:8080`

You should see...

Greetings from Spring Boot!





