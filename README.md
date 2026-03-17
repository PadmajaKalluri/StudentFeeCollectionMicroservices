# StudentFeeCollectionMicroservices

**3.Project Overview**
A Spring Boot based microservices system designed to manage student records, collect school fees, and generate digital receipts using **Spring Boot 3.5.6**. The system demonstrates Domain Driven Design, RESTful API best practices, inter-service communication, and API documentation using Swagger.

Features include:

Student management APIs

Fee collection and payment processing

Automatic receipt generation

Swagger API documentation

H2 in-memory database

The system consists of three independent services:
- Student Service
- Payment Service
- Receipt Service

Each service is independently deployable and follows **Domain-Driven Design (DDD)** principles.

**2.Microservice Architecture**
The system is divided into three microservices.

**A.Student Service**
**Role**:Student Service is a Spring Boot microservice responsible for managing student information
Manage student records

Provide student data to other services

**Responsibilities**

1.Add student

2.Get student by ID

3. List students

**B.Payment Service**

**Role**:This service provides student information required by the Payment Service during fee transactions.

1. Process payments

2. Gets payments made by Students
**Responsibilities**

Process fee payments

Validate student

Store transaction

Trigger receipt creation

**C.Receipt Service**

**Role**: Microservice responsible for generating and retrieving payment receipts for student fee transactions.

Generate payment receipts

**Responsibilities**

Generate receipt

Fetch payment

Fetch student details

Return receipt view

**3. Technology Stack**
| Technology               | Purpose                     |
| ------------------------ | --------------------------- |
| Spring Boot 3.5.6        | Microservice framework      |
| Spring Web               | REST APIs                   |
| Spring Data JPA          | Data persistence            |
| H2 Database              | In-memory DB                |
|  RestTemplate            | Inter-service communication |
| Swagger                  | API documentation           |
| JUnit + Mockito          | Unit testing                |
| Maven                    | Build tool                  |
| Postman                  | API testing                 |


**4. Domain Driven Design (DDD)**
**Bounded Contexts**
Domain	            Service
Student Management	Student Service
Payment Processing	Payment Service
Receipt Generation	Receipt Service

Each microservice owns its own database.

**5.Inter-Service Communication**
Payment → Student Service
Payment → Receipt Service

**6.Postman Collection APIs**

**A.Student API's**
POST /students/add/v1
GET /students/getAllStudents
GET /students/{id}

**B.Payment APIs**
POST /payments/makePayment/v1
GET /payments/{id}
GET /payments/student/{studentid}

**c.Receipt APIs**
POST /receipts//generateReceipt/v1

**7.Unit Testing**

Example using JUnit + Mockito

StudentServiceTest
PaymentServiceTest

**8.Running the Project**

Running the Services

**Build**
mvn clean install

**Run**
mvn spring-boot:run

**Service ports**

**Service**	        **Port**
Student Service	    8081
Payment Service	    8082
Receipt Service	    8083

**Swagger URLs**

**Service**         **Url**
student-service     http://localhost:8081/swagger-ui.html

payment-service     http://localhost:8082/swagger-ui.html

receipt-service     http://localhost:8083/swagger-ui.html

**10Optional Improvements** 

we can add:

API Gateway (Spring Cloud Gateway)

Service Discovery (Eureka)

Docker & Kubernetes

Centralized logging



