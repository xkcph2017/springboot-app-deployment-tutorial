# Spring Boot Deployment Tutorial
I'll use my very own project to demonstrate how to use Spring Boot and
if you are interested in the project itself, please refer to the 
[original repo of this project](https://github.com/xdvrx1/lightweight-web-server). 

This repo focuses on how to use the Spring Boot to create
a production-grade executable jar file. Spring Boot is concerned with the 
infrastructure while you focus on writing your program. It's really that simple to build 
and run **any** of your existing Java program through Spring Boot.

First, there must be the `maven plugin` to create the executable jar file
in the `pom.xml`:

```
<groupId>org.springframework.boot</groupId>
<artifactId>spring-boot-maven-plugin</artifactId>
```

Second, you tell Spring Boot the main method of your program 
because it has its own main method. 

```
<configuration>
	<mainClass>xdvrx1_serverProject.MainMethod</mainClass>
</configuration>	
```

And finally, when your program launches GUI, you must set 
the headless mode in the SpringMainMethod file to false or else it 
will throw a `HeadlessException`. This web server is not yet complete
but my plan is to add GUI.

```
SpringApplicationBuilder builder = 
	new SpringApplicationBuilder(SpringMainMethod.class);
	builder.headless(false);
	ConfigurableApplicationContext context = builder.run(args);
```

What others are doing is relying on `CommandLineRunner`. This is needed
when you want to trap user inputs on the command line once the
Spring Boot is started and before your program runs. In our case here,
we don't need that. 
  
See the project for the complete codes and setup!

## Q&A

If you have questions, please feel free to ask me: 

<mongAlvarez@gmail.com>
   
You can also create a pull request or raise
an issue to start the discussion or query/ies.

## Compile, Build & Run
Before you compile and build, make sure you are at the project directory
`SpringBootProjectDir`. Take note also, I'm using Maven build tool here. 

In Windows,

to package your program as an executable jar file:

	mvn clean package

to simply clean and compile:

	mvn clean compile

to just clean your project:

	mvn clean

to run the program:

	mvn spring-boot:run

to build and run the program:

	mvn clean install


## Contributing

1. Fork it!
2. Then, made changes, and create a pull request. 
I'm much more willing to collaborate with you!

## License

MIT - the permissive license
