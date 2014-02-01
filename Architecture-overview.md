# Architecture overview

The way Sonar works is that plugins are installed onto the server.  Sonar-runner then downloads these plugins (in .jar files) and then they are available in the local environment.

## Debugging tip

It is possible to copy the built .jar file into the correct folder in ~/.sonar/cache on the local machine.  In this way changes to sonar-runner behavior can be tested without changing things on the remote server.