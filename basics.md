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

The first thing to take note of is the <parent> element and, more specifically, its
<version> child. This specifies that your project has spring-boot-starter-parent
as its parent POM. Among other things, this parent POM provides dependency
management for several libraries commonly used in Spring projects. For those
libraries covered by the parent POM, you won’t have to specify a version, because it’s
inherited from the parent. 