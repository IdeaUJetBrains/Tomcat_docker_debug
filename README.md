Clone this repository as a new IntelliJ IDEA project and try running and debugging a Java Enterprise web application using Docker Compose and remote debug.

# How to run and debug

1. Build the WAR artifact: **Build** -> **Build Artifacts**
2. Open `docker-compose.yaml` and click the icon with green arrows in the gutter to run it via Docker Compose.
3. Wait for the Tomcat container to start (the container log show say "Server startup in [xxxxx] milliseconds").
4. Open this URL, which should return `Hello, World!` http://localhost:8888/Tomcat_docker_debug-1.0-SNAPSHOT/api/hello-world
5. Run the `remote_tomcat_debug` configuration to attach the debugger.
6. Set a breakpoint, for example, on the REST method `hello()`, where it returns "Hello, World!"
7. Refresh or open the URL again http://localhost:8888/Tomcat_docker_debug-1.0-SNAPSHOT/api/hello-world

Result: it should stop at the breakpoint.

> You can add the Docker Compose run configuration as a **Before launch** task in the `remote_tomcat_debug` configuration.
> However, there is currently an [issue](https://youtrack.jetbrains.com/issue/IDEA-172781) with this
> that the remote debug configuration starts before the Docker Compose has time to start the service.
> This issue will be fixed in 2023.3.

This tutorial uses Tomcat 10.0 with Jakarta EE 9.1.
You can choose a different combination:
- Tomcat 10.1 + Jakarta EE 10
- Tomcat 9 and earlier + Java EE 8
