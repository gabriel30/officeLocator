# officeLocator

This application expose rest api for management of the different offices located in different timezone.

=============
Requeriments
=============
	Compilation
	- Spring Roo 2.0.0.M1
	- Maven 3.3.3

	Execution
	- MySQL
	- Tomcat

============
Instruction
============

The next instructions will help you to execute the application:

(For compilation, you need to have Spring Roo and Maven correct configured in you machine)
1. Initiate an MySQL server instance. The application are configured to use a MySQL database called "officelocator" in the host 127.0.0.1 and port 3036 (see database.properties in the code)
2. In the MySQL server create the schema "officelocator"
3. To initiate the application. Using an OS terminal go to application directory and type "mvn clean tomcat:run", this will initiate the application using embbeded tomcat server.

=============
REST SERVICES
=============
	
Desciption: 	List offices open now
Http method: 	GET
URL:			http://127.0.0.1:8080/officeLocator/office/openNow
Response:		
				HttpStatus 200 "OK" in case of success
				Example JSON:
					[
						0:  {
						officeId: "4"
						officeName: "A"
						cityId: "1"
						cityName: "Madrid"
						stateId: "1"
						stateName: "Comunidad de Madrid"
						countryId: "34"
						countryName: "Spain"
						openFrom: "3:00:00"
						openUntil: "10:00:00"
						}
					]
				
				HttpStatus 500 "500 Internal Server Error" in case of failed

Desciption: 	List all offices
Http method: 	GET
URL:			http://127.0.0.1:8080/officeLocator/office/
Response:		
				HttpStatus 200 "OK" in case of success
				Example JSON:
					[
						0:  {
						officeId: "4"
						officeName: "A"
						cityId: "1"
						cityName: "Madrid"
						stateId: "1"
						stateName: "Comunidad de Madrid"
						countryId: "34"
						countryName: "Spain"
						openFrom: "3:00:00"
						openUntil: "10:00:00"
						}
					]
				
				HttpStatus 500 "500 Internal Server Error" in case of failed
				
Desciption: 	Show specific office details
Http method: 	GET
URL:			http://127.0.0.1:8080/officeLocator/office/{id}
Response:		
				HttpStatus 200 "OK" in case of success
				Example JSON:
					
					{
						officeId: "4"
						officeName: "A"
						cityId: "1"
						cityName: "Madrid"
						stateId: "1"
						stateName: "Comunidad de Madrid"
						countryId: "34"
						countryName: "Spain"
						openFrom: "3:00:00"
						openUntil: "10:00:00"
					}
					
				
				HttpStatus 500 "500 Internal Server Error" in case of failed


Desciption: 	Create Office
Http method: 	POST
URL:			http://127.0.0.1:8080/officeLocator/office/
BODY (json example):			
				{
				  "name": "New Office",
				  "city": {
					"id": 1
				  },
				  "openFrom": "11:00:50",
				  "openUntil": "21:00:10"
				}

Content-Type: 	application/json;charset=UTF-8 
Response:		HttpStatus 201 "Created" in case of success / HttpStatus 500 "500 Internal Server Error" in case of failed
