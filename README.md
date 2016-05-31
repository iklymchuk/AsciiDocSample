##Requirements.

JDK: jdk1.7.0_79.jdk
Maven: apache-maven-3.3.3
Jenkins: Installation
IDE: IntelliJ IDEA 14.1.4

Official: https://wiki.jenkins-ci.org/display/JENKINS/Plugin+tutorial


1. Update maven settings

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

2. ```mvn -U org.jenkins-ci.tools:maven-hpi-plugin:create```

3. ```cd newly-created-directory```
   ```mvn package```

4. ```mvn install```

5. ```mvn hpi:run```
