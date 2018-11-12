This is a proof of concept of configuration microservice which uses a Kafka topic as its data store.

It is dynamic and can be updated at runtime to alter system behavior live.  We provide a RESTful POST endpoint for that purpose
but you can also directly post to the Kafka config topic from any other source.

If a configuration value already exists, it will be overwritten.  If the new value is an empty String, the configuration key 
will be deleted.

The system is currently configured to start up and immediately load all configuration values from the beginning of time.  

Future plans include:  
* Allowing system to start empty
* Export/Import of current configuration 
* Starting a new instance and loading configuration from another running instance
* Controls to clear configuration, reload it from the beginning of the era, or reload it from a particular time

In order to run and test this you will need:
* A copy of gradle
* A recent JDK
* A running instance of Kafka
* Either curl or Postman