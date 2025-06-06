dependencies {
    implementation 'org.glassfish.jersey.core:jersey-server:3.1.2'
    implementation 'org.glassfish.jersey.containers:jersey-container-grizzly2-http:3.1.2'
    implementation 'org.glassfish.jersey.inject:jersey-hk2:3.1.2'
}



import jakarta.ws.rs.GET;
import jakarta.ws.rs.Path;
import jakarta.ws.rs.Produces;
import jakarta.ws.rs.core.MediaType;

@Path("/hello")
public class HelloResource {

    @GET
    @Produces(MediaType.TEXT_PLAIN)
    public String hello() {
        return "Hello from Jersey!";
    }
}


import org.glassfish.grizzly.http.server.HttpServer;
import org.glassfish.jersey.grizzly2.httpserver.GrizzlyHttpServerFactory;
import org.glassfish.jersey.server.ResourceConfig;

import java.net.URI;

public class Main {
    public static void main(String[] args) {
        final String BASE_URI = "http://localhost:8080/";
        final ResourceConfig config = new ResourceConfig().packages("com.example");

        HttpServer server = GrizzlyHttpServerFactory.createHttpServer(URI.create(BASE_URI), config);
        System.out.println("Jersey app started at " + BASE_URI + "hello");
        Runtime.getRuntime().addShutdownHook(new Thread(server::shutdownNow));
    }
}
