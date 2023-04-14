#=================================================================================================================
# IntelliJ IDEA
#=================================================================================================================
# Steps to run/debug:
#  - Run this compose file via the green gutter
#  - Wait until the application is deployed (it takes some time - in container logs appears "Server startup in [xxxxx] milliseconds"):
#    http://localhost:8888/Tomcat_docker_debug-1.0-SNAPSHOT/api/hello-world
#  - Run the "remote debug configuration
#  - Set breakpoints, for example on the rest method "hello()" which should return "Hello, World!"
#  - Open once more: http://localhost:8888/Tomcat_docker_debug-1.0-SNAPSHOT/api/hello-world
# Result: it stops at the breakpoint

#=================================================================================================================
#  Note1: this example project is very simple to create (see the picture of the wizard settings):
#  - File->New->Project
#  - Select "Jakarta EE"
#  - Select "REST service" template
#  - Select tomcat (for example 10.0)
#  - Select "java 17"
#  - Next
#  - Select "Jakarta EE 9.1" if another is selected
#  - Create

#  Note2: the correspondence of Tomcat versions to Jakarta EE, otherwise it wouldn't work:
#  tomcat10.1 + Jakarta EE 10
#  tomcat10.0 + Jakarta EE 9.1
#  tomcat 9 and low + JavaEE 8

#  Note3: Build the project and artifacts(war file) before the steps below: Build->Build Project, Build->Build Artifacts

#  Note3:
#  As soon as this issue will be fixed we can add this compose run configuration as the "Before launch" task in the remote run configuration and run all in one click.
#  See and vote https://youtrack.jetbrains.com/issue/IDEA-172781
#  For now it wouldn't wait until tomcat starts inside the container and runs remote debug too early.
