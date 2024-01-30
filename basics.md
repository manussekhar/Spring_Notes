At its core, Spring offers a container, often referred to as the Spring application con-
text, that creates and manages application components. These components, or beans,
are wired together inside the Spring application context to make a complete applica-
tion, much like bricks, mortar, timber, nails, plumbing, and wiring are bound together
to make a house.
The act of wiring beans together is based on a pattern known as dependency injection
(DI). Rather than have components create and maintain the life cycle of other beans
that they depend on, a dependency-injected application relies on a separate entity
(the container) to create and maintain all components and inject those into the beans
that need them. This is done typically through constructor arguments or property
accessor methods.

Java-based configuration offers several benefits over XML-based configuration,
including greater type safety and improved refactorability. Even so, explicit configura-
tion with either Java or XML is necessary only if Spring is unable to automatically con-
figure the components.
Automatic configuration has its roots in the Spring techniques known as autowiring
and component scanning. With component scanning, Spring can automatically discover
components from an application’s classpath and create them as beans in the Spring
application context. With autowiring, Spring automatically injects the components
with the other beans that they depend on.
More recently, with the introduction of Spring Boot, automatic configuration has
gone well beyond component scanning and autowiring. Spring Boot is an extension
of the Spring Framework that offers several productivity enhancements. The most well
known of these enhancements is autoconfiguration, where Spring Boot can make rea-
sonable guesses at what components need to be configured and wired together, based
on entries in the classpath, environment variables, and other factors.

**Spring boot pom structure**
Parent
------------
The first thing to take note of is the <parent> element and, more specifically, its
<version> child. This specifies that your project has spring-boot-starter-parent
as its parent POM. Among other things, this parent POM provides dependency
management for several libraries commonly used in Spring projects. For those
libraries covered by the parent POM, you won’t have to specify a version, because it’s
inherited from the parent. 

Starter Dependencies
----------------------
Spring Boot starter dependencies are spe-
cial in that they typically don’t have any library code themselves but instead transi-
tively pull in other libraries. These starter dependencies offer the following primary
benefits:
 Your build file will be significantly smaller and easier to manage because you
won’t need to declare a dependency on every library you might need.
 You’re able to think of your dependencies in terms of what capabilities they
provide, rather than their library names. If you’re developing a web application,
you’ll add the web starter dependency rather than a laundry list of individual
libraries that enable you to write a web application.
 You’re freed from the burden of worrying about library versions. You can trust
that the versions of the libraries brought in transitively will be compatible for a
given version of Spring Boot. You need to worry only about which version of
Spring Boot you’re using.

Spring Boot plugin
--------------------
 It provides a Maven goal that enables you to run the application using Maven.
 It ensures that all dependency libraries are included within the executable JAR
file and available on the runtime classpath.
 It produces a manifest file in the JAR file that denotes the bootstrap class
(TacoCloudApplication, in your case) as the main class for the executable JAR.


@SpringBootApplication - composite annotation that consists of
1. @SpringBootConfiguration—Designates this class as a configuration class
2. @EnableAutoConfiguration—Enables Spring Boot automatic configuration.
3. @ComponentScan—Enables component scanning. This lets you declare other
classes with annotations like @Component, @Controller, and @Service to have
Spring automatically discover and register them as components in the Spring
application context.

@SpringBootTest - which is itself annotated with @ExtendWith(SpringExtension.class), to
add Spring testing capabilities to JUnit 5

