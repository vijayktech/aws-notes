Configuration 

POM.xml 

	• Add below dependency 
		a. spring-cloud-function-adapter-aws  
			- The AWS adapter takes a Spring Cloud Function app and converts it to a form that can run in AWS Lambda.
		b. aws-lambda-java-events
		c. aws-lambda-java-core  -> To enable Lambda 
		d. Exclude from starter-test dependency
		<exclusion>
		   <groupId>org.junit.vintage</groupId>
		   <artifactId>junit-vintage-engine</artifactId>
		</exclusion>
		
		
	• Add shade plugin for reduce the generated package size.
AKIA6DM4WP4CCP7KOBOO
vdf+SPh81WsgDCaS/O5RlAx+W3gnCWpLGvkQQ8bu


		<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-shade-plugin</artifactId>
            <version>3.2.4</version>
            <configuration>
                <createDependencyReducedPom>false</createDependencyReducedPom>
            </configuration>
            <executions>
                <execution>
                    <phase>package</phase>
                    <goals>
                        <goal>shade</goal>
                    </goals>
                </execution>
            </executions>
        </plugin>
    </plugins>
</build>



Create one of the Handler with help of any Handler. 
3 Types of Handler for Lambda Implementation
	1. Creating a custom MethodHandler.
	2. Implementing the RequestHandler interface.
	3. Implementing the RequestStreamHandler interface.

		
AWS Configuration
	1. Upload the jar in AWS Lambda.
	2. Test it.


GitHub Project : https://github.com/vijaykonkata/aws-lambda-demo 
		
Reference :  <https://www.appsdeveloperblog.com/build-and-deploy-a-serverless-spring-boot-web-application-with-aws-lambda/> 
![image](https://github.com/vijayktech/aws-notes/assets/143890916/4fc07ca4-6136-45c8-9861-a357a96f6133)
