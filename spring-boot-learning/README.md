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
      <artifactId>spring-cloud-starter</artifactId>
    </dependency>
  ```
*  ii add below line in applicatin.properties file
*  ```
   eureka.instance.client.serverUrl.defaultZone=http://localhost:8761/eureka/
   ```
   Load balancing:
* what if our one object question get down ,when we will send request from quiz then we cant get list of question in this case we can create a instance of question 
  (mvn-package-copy jarfile run it) . now change the port number of original question instance. and run it. now we can see our two question object is running with 
  two different port.
* Now we have to add load balancing dependency ,step:2 @FeingClient(name="QUESTION-SERVICE") RUN it.we can check our eureka server .it will show 2 instances of
  question is running. whenever one instance will go down automatically load balance will manage it from other instance.
