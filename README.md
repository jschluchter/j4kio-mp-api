# MicroProfile Hello Azure Sample

This is a sample Eclipse [MicroProfile](https://microprofile.io) project that exposes one REST API using JAX-RS, and enables the Health API.

Diving into the `src` directory, we will eventually discover the `Application` class reproduced below:

```java
@ApplicationPath("/api")
public class Application extends javax.ws.rs.core.Application { }
```

The `@ApplicationPath("/api")` annotation specifies the base endpoint for this microservice - that is, that all endpoints will have `/api` preceed the rest of the URL required to access any specific REST endpoint.

Inside the `api` package is a class named `API`, which contains the following code:

```java
@ApplicationScoped
@Path("/api")
public class API {

  @GET
  @Path("/hello")
  @Produces(TEXT_PLAIN)
  public String info() {
    return "Hello, Azure!";
  }

  @GET
  @Path("/j4k")
  @Produces(TEXT_PLAIN)
  public String info() {
    return "Hello, J4k!";
  }
}
```


