To deploy a java app with multiple profiles
all we need is create multiple application-[env].yml files

don't use spring.profiles.active=dev in application.yml. It will force the app to use only dev profile.

Just build the app with the maven command:

```mvn clean package -DskipTests```

If you want to run it in terminal, use the command:

```java -jar target/app.jar --spring.profiles.active=[env]```

Make sure to use server.port=5000 for the deployed version.

To make it work in production.
Create the environment variable SPRING_PROFILES_ACTIVE=[env] in the production environment, if it is ELB, just create and environment variable.

To run it in EC2 should be a similar process.
