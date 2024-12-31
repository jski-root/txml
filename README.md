# Trap XML (txml)
 Trap XML is a modeling language to describe a Domain to Environment Generation, Deployment and Application Processes using a mix of BPMN, DMN, BPEL (without WS) and XSD. txml is used to describe an Enterprise's domains and model them into a particular target such as Jakarata EE, Spring, C, GO, Python, Web Assembly and many more with XSLT.
 
 This application is alignment with Model Base Software Engineering (MBSE) tools that can map **txml** to SysML, XMI, TOGAF, NAF and DoDAF documents. **Models** are first class citizens in txml. Integrations with PM tools for scheduling and traceability of assignments and Large Language Models (LLM) or Machine Learning (ML) to accelerate Developer's productivity. The LLM or LM is to assist in with the quering and menial tasks such as reports and boilerplate coding that doesnt require any critical thought or analysis!
 
 Ideally the project will generate a neurosymbolic agent that can reason about your domain. This is where Java 21 comes into play with Vectors and Algebraic Data Types (ADT) will be considered and LLMs to handle generalized boilerplate code or framework idiosyncrasies. With Vectors and ADTs we can create solver for symbolic logic of the domain(s), may consider using Z3 or JSolver.
 
## Standards
 Using BPMN's extension element, we can insert the BPEL algorithm. With BPMN's start element, will be transformed into a UI input element or Web Service endpoint.
 
 - BPMN 2.0
 - BPEL 2.0 without WS
 - XSD
 - XSLT
 
## Features
 The code will have the ability to deploy to an image with users and roles defined by a standard protocol such as OAuth 2.0 or LDAP
 
 - Simulations
 - Code Generation
 - LLM querying of Domains/Models
 
## Target Audiance
 Business Domains, Simulations and Data Intensive Applications.
 
## What TXML **NOT** Targeting
 txml is not considering First Person Shooter (FPS) games or game engines in design.
 
## Target Environment
 Targeting a Jakarta EE micro profile environment such as Quarkus and HTMX front end for the Application. Java 21 for modeling and generating from XSLT. Application will work as Desktop or Server Side Rendering. Shall have the exact same behavior.
 
## Trap XML Development
 This repository relies heavly on BPMN, XSD and BPEL editors with Maven Plugins. txml shall eat its own dog food and generate its self through the txml model.
 
## TXML Agent
 Shadow Agent/OS in lieu of containers. install an agent on base image and setup with certificates and configure git URLs to txml shall build the domain(s) on that asset
 
## Case Against Containerization
 seems ineffecient, why build a cluster of computers that run containers that behave like they are running on a monolith. It seems like that running JavaEE on the cluster and have the deployment of EAR file full of @Stateless EJBs would be more effecient and easier to manage.
 
## YAML or JSON Considerations
 Just say no! Both of these markups are useless and the software industry seems to be getting worse as time goes on. YAML has no schema definitions and JSON is just a serialization of data for one particular language.  
 
## Logic &equiv; Logic
 p and q is also q and p, therefore an algorithm that is built in Java can also be built in GO.
 
## &#8253; TXML Markdown
 Using the Interrobang character for markdown of txml is ideal as it is not a used character in text. Has a Creational Builder Pattern vibe to it.

```c
\\this is a comment!

\\notice that strings are not encapsulated with double quotes!
‽.set_parameter(Semper fi).value(fuck off \‽, prints literal interrobang)


‽.import(http://oracle.database.com/V5/dkuie).as(DB)
‽.import(http://html.com/5).as(http)
‽.import(http://www.omg.org/spec/BPMN/20100524/MODEL).as(BPMN)
‽.import(http://go.me).as(GO)

\\declarations can be accessed in scoped by ‽.{name}, these are definitions and not memory allocations
‽.declare(name).as(text).max_length(32) \\text is same as string, except the word 'text' make literal sense.
\\ALL text is never ending UTF-8

\\ to print '\\' then `\\ 

\\ to print '|' then `|

\\declarations can have spaces! makes documenation nicer :-)
‽.declare(person's picture).as(image/png).max_size(16MB)


‽.declare(age).as(u16) \\i8,i16,i32,i64,i128,u8,u16,u32,u64,u128

‽.http.server().set_port(8080)
	.pool(‽DB.database().port(1700).user_name(jordan).schema(users))
	.services()
		.add(‽.GET(/greeting/‽.{name}).return_type(text).response(hello ‽.{name}).catch(e -> e.printStack))
		.add(‽.file(/usr/bin/hyt.xml))
		.add(‽.GET(/user/‽.{name}).return_type(xml|json).reponse(
			‽.(DB).execute(
				select fname, lname, age, phone \\automatically map this to xml or json response, dont over think it
				from profile
				where lname = ‽.{name}) \\This is automaically paramerterized, NO Dynamic SQL!
			.catch()) \\ will not compile without this catch!
		.add(‽.GET(/user/‽.{name}/‽.{age}).return_type(xml|json).reponse(
			select fname, lname, age, phone
			from ‽.{name}                                      //   <- ERROR
			where age = ‽.{age}).catch())
		.add(‽.GET(/user/‽.{name}/image)
			.return_type(image/png)
			.response(
				‽.program
					.declare(userid).as(uuid)
					.step(
						‽.DB.execute(
							select A.userid
							into ‽.{userid}
							from users A
							where A.lname = ‽.{name}
						).catch(\\do somthing here))
					.step
						\\step has built in mapping and conditionals
						.set(‽.{person's image} | ‽.file.read(/app/images/‽.{userid}/image.png)) 
					.step
						.if(‽.{person's image} is null)
							.then
								.return(404)
						.else
							.return(‽.{person's image})
				.catch
					.log(‽.stack_trace)
					.return(500)
			).crop().width(100px).height(100px).channel(red).(‽ * 4)
		.add(‽.POST(/user/‽.{name})
			.declare(name).as(text) \\local variable, but uses age's gobal definition
				.return_type(text)
					.response(
					<<<<<<<BPMN Diagram>>>>>>
					‽.{name}
					‽.{age}
					
				)
		.add(‽.POST(/user/{name}).return_type(text).response(
			<!--<<<<<<GO PROGRAM>>>>>-->
			‽.GO.arguments(‽.{name} | ‽.{age} | im a string) \\use pipe to seperate aruments to functions
			.main(
				package main
				
				import (
   					 "fmt"
  					  "os"
				)

				func main() {

    					argsWithProg := os.Args
    					argsWithoutProg := os.Args[1:]

    					arg := os.Args[3]

    					fmt.Println(argsWithProg)
    					fmt.Println(argsWithoutProg)
   					 fmt.Println(arg)
				}		
			).argument({name}).argument(‽.//age).argument(‽./body/person/nickname)
		.add(‽.GET(/user/{name}).return_type(text).response(
			<<<SPREAD SHEET>>>
			<<<BPEL>>>
			<<<PYTHON>>>
			<<<DMN>>>
			<<<JS>>>
			<<<HTML>>>
			<<<HTMX>>>
			<<<XML>>>

			<<<RICH TEXT>>>

			<<<PDF>>>
			<<<any thing u can think of>>>
			‽.
		))
		.add(‽.GET(/user).param(age).param(lname).param(fname)
			 .param(role).return_type(ANY).response(
			‽.criteria()
				.table(users).select(lname, fname, age).where(‽.{lname}, ‽.{fname}, ‽.{age})
				.table(roles).select(name).where(name = ‽.{role})
				.table(event)
		).catch()



.stdin().

```
 
## Project Roadmap
 This will outline this project's roadmap. This is still in inital phase.
 
 1. Create Mission Statement
 1. Clarify the engineering of project
 1. MVP of a simple txml
 1. XSLT for JarkataEE
 1. XSLT for GO
 1. Create an agent for Debian
 1. Create a tool to query domain to generate **nuisance compliance reports**
 1. ANTLR or Xtext DSL to build txml files (think markdown for txml)