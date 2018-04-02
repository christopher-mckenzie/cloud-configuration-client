## configuration client

* spring boot application that uses config server to read configuration
* refreshes configuration to reflect changes to config server on demand without jvm restart
* properties configured in the client's .yml must be read before getting config info from config server
    * this occurs during the bootstrap phase
    * thus need to define application name and cloud config uri in bootstrap.yml
* requirement - need to enable a refresh endpoint
    * in application.yml add management.endpoints.web.exposure.include:*
* client can access any value in config server using traditional mechanisms i.e. @Value, @ConfigurationProperties
* annotate class with @RefreshScope to enable property refresh for a given class
