
  implementation 'org.apache.tomcat.embed:tomcat-embed-core:9.0.85'
    implementation 'org.apache.tomcat.embed:tomcat-embed-jasper:9.0.85'
    implementation 'jakarta.servlet:jakarta.servlet-api:5.0.0'



  int port = 8080;
        String baseDir = Files.createTempDirectory("tomcat").toString();

        Tomcat tomcat = new Tomcat();
        tomcat.setPort(port);
        tomcat.setBaseDir(baseDir);
        tomcat.getConnector(); // trigger default connector

        tomcat.addContext("", baseDir);

        Tomcat.addServlet(tomcat.getHost().findChild(""), "helloServlet", new HttpServlet() {
            @Override
            protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws IOException {
                resp.setContentType("text/plain");
                resp.getWriter().write("Hello from Tomcat Embedded!");
            }
        });

        tomcat.addServletMappingDecoded("/", "helloServlet");

        tomcat.start();
        tomcat.getServer().await();
    }
