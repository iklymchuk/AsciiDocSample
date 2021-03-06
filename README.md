##Sample Jenkins Plugin configuration

Maven configuration should be ubdated as bellow:

 ```   cat /home/iklymchuk/.m2/settings.xml ```
```
<settings>
  <localRepository>/home/iklymchuk/.m2/repository/</localRepository>
  <pluginGroups>
    <pluginGroup>org.jenkins-ci.tools</pluginGroup>
  </pluginGroups>

  <profiles>
    <!-- Give access to Jenkins plugins -->
    <profile>
      <id>jenkins</id>
      <activation>
        <activeByDefault>true</activeByDefault> <!-- change this to false, if you don't like to have it on per default -->
      </activation>
      <repositories>
        <repository>
          <id>repo.jenkins-ci.org</id>
          <url>http://repo.jenkins-ci.org/public/</url>
        </repository>
      </repositories>
      <pluginRepositories>
        <pluginRepository>
          <id>repo.jenkins-ci.org</id>
          <url>http://repo.jenkins-ci.org/public/</url>
        </pluginRepository>
      </pluginRepositories>
    </profile>
  </profiles>
</settings>
```
Then we can started:

1. Go to workspace

   ```mvn -U org.jenkins-ci.tools:maven-hpi-plugin:create```
   
   and set up artifactId and projectId

2. ```cd newly-created-directory```
   ```mvn package```

3. ```mvn install```

4. ```mvn hpi:run```

If all configured correctly you will see Jenkins home here ```localhost:8080/jenkins```
