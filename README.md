# Spring Native problem with Spring ORM

This repo is showcasing a problem in building a Spring Native image when having `spring-orm` as a dependency.

In order to see the problem run:

```shell
./mvnw package -Pnative -DskipTests   
```

it will fail with:

```
========================================================================================================================
GraalVM Native Image: Generating 'demo'...
========================================================================================================================
[1/7] Initializing...
                                                                                    (3.8s @ 0.07GB)
Error: Cannot find org.springframework.orm.jpa.persistenceunit.DefaultPersistenceUnitManager.determineDefaultPersistenceUnitRootUrl, org.springframework.orm.jpa.persistenceunit.DefaultPersistenceUnitManager can not be loaded, due to javax/persistence/spi/PersistenceUnitInfo not being available in the classpath. Are you missing a dependency in your classpath?
Error: Use -H:+ReportExceptionStackTraces to print stacktrace of underlying exception
------------------------------------------------------------------------------------------------------------------------
                         0.2s (4.5% of total time) in 8 GCs | Peak RSS: 0.58GB | CPU load: 6.13
------------------------------------------------------------------------------------------------------------------------
```