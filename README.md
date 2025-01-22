Cloud Config Server
This repository contains the configuration files for a Spring Cloud Config Server. The server is configured to fetch properties from this Git repository and serve them to microservices.

Configuration Files
The following configuration files are included in this repository:

eureka-server.properties: Configuration for the Eureka Server.

microservice-commandes.properties: Configuration for the "Commandes" microservice.

microservice-produits.properties: Configuration for the "Produits" microservice.

Config Server Properties
The main configuration for the Spring Cloud Config Server is defined in the application.properties file. Below are the key properties:

properties
Copy
spring.cloud.compatibility-verifier.enabled=false
spring.application.name=configmicro
server.port=9101
spring.cloud.config.server.git.uri=https://github.com/chilleflx/cloud-config.git
spring.cloud.config.server.git.default-label=main

# Log level configuration
logging.level.root=INFO
logging.level.com.mcommerce.config.server=INFO
logging.level.org.springframework.boot.web.embedded.tomcat=INFO
Explanation of Properties
spring.cloud.compatibility-verifier.enabled=false: Disables the compatibility verifier.

spring.application.name=configmicro: Sets the application name to configmicro.

server.port=9101: Configures the server to run on port 9101.

spring.cloud.config.server.git.uri: Specifies the Git repository URL where the configuration files are stored.

spring.cloud.config.server.git.default-label=main: Sets the default Git branch to main.

logging.level.root=INFO: Sets the root logging level to INFO.

logging.level.com.mcommerce.config.server=INFO: Sets the logging level for the com.mcommerce.config.server package to INFO.

logging.level.org.springframework.boot.web.embedded.tomcat=INFO: Sets the logging level for the embedded Tomcat server to INFO.

How to Use
Clone the Repository: Clone this repository to your local machine or server where the Spring Cloud Config Server is running.

bash
Copy
git clone https://github.com/chilleflx/cloud-config.git
Run the Config Server: Ensure that the application.properties file is correctly configured and then start the Spring Cloud Config Server.

Access Configuration: Microservices can access their configuration by pointing to the Config Server's URL, typically http://localhost:9101.

Example Microservice Configuration
Commandes Microservice
The microservice-commandes.properties file contains specific configurations for the "Commandes" microservice. Here is an example:

properties
Copy
# Example properties for the Commandes microservice
commandes.service.url=http://localhost:8081
commandes.service.timeout=5000
Produits Microservice
The microservice-produits.properties file contains specific configurations for the "Produits" microservice. Here is an example:

properties
Copy
# Example properties for the Produits microservice
produits.service.url=http://localhost:8082
produits.service.timeout=3000
Logging Configuration
The logging configuration is set to INFO level for the root logger, the config server package, and the embedded Tomcat server. You can adjust these levels as needed for debugging or production environments.

Contributing
If you would like to contribute to this repository, please fork the repository and create a pull request with your changes.

License
This project is licensed under the MIT License - see the LICENSE file for details.
