# sparkjava-war-example
Build war with maven and sparkjava framework

Steps:

1. Download a fresh [Tomcat 8 distribution](https://tomcat.apache.org/download-80.cgi)

2. Clone this repository to your local machine
3. Run mvn package:
4. Copy the generated `sparkjava-hello-world-1.0.war` to the Tomcat `webapps` folder
5. Start Tomcat by running `bin\startup.bat` (or `bin\startaup.sh` for Linux)
in here : /usr/local/Cellar/tomcat/10.0.23/libexec/bin
replace 10.0.23 which version tomcat you are using !

5. Tomcat will automatically deploy the war
6. Open [http://localhost:8080/sparkjava-hello-world-1.0/hello](http://localhost:8080/sparkjava-hello-world-1.0/hello) in your browser

- Note:
1. cai chinh xac version tomcat 8.0 moi deploy duoc !
3. Neu loi :
Failed to execute goal org.apache.maven.plugins:maven-war-plugin:2.2:war (default-war) on project sparkjava-hello-world: Execution default-war of goal org.apache.maven.plugins:maven-war-plugin:2.2:war failed: Unable to load the mojo 'war' in the plugin 'org.apache.maven.plugins:maven-war-plugin:2.2' due to an API incompatibility: org.codehaus.plexus.component.repository.exception.ComponentLookupException: Cannot access defaults field of Properties

---> define version cao hon de chay: add to pom.xml this code:
```
			<plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-war-plugin</artifactId>
                <version>3.2.3</version>
                <configuration>
                    <failOnMissingWebXml>false</failOnMissingWebXml>
                </configuration>
            </plugin>
```

Link fix: https://github.com/jhipster/generator-jhipster/issues/10104

Success:
http://localhost:8080/sparkjava-hello-world-1.0/hello
Hello Tin Hoc That La Don Gian5555555555

