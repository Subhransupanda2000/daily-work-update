# Microservice architecture
* Microservice architecture is a design pattern for building distributed software applications composed of small, independent services that communicate over a network. Each service focuses on a specific business function and can be developed, deployed, and scaled independently.
* ex- lets take a example of a quiz game .In a single quiz we have multiple questions so we will create 2 micro component here quiz and question. we can add both the project throug maven '+' icon .Now we need to make both project entities cortoller and services.
* After completing above things we can map both the project using FeignClient dependency.
  ```
  <dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-starter-openfeign</artifactId>
		</dependency>
  ```
# Server Registry
* A service registry is a key component in a microservice architecture that helps manage and keep track of all the microservices available in a distributed system. It serves as a central directory where microservices register themselves and from which other microservices can discover and locate them. This dynamic discovery mechanism is essential for maintaining flexibility and scalability in a microservice environment.
* Now here quiz and questions are client and eureka server act as server registry.we need to register quiz and question as registry with below steps:
* i.add these dependency
  ```
  <dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
		</dependency>
  		<spring-cloud.version>2023.0.2</spring-cloud.version>
    <dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
		</dependency>
  ```
*  ii add below line in applicatin.properties file
*  ```
   eureka.instance.client.serverUrl.defaultZone=http://localhost:8761/eureka/

   ```
