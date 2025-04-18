# Task 8: Jenkins + Maven Hello World

This repository is part of my DevOps internship at Elevate Labs.  
The task was to set up a simple CI build pipeline using Jenkins and Maven for a basic Java project.

## 📌 Objective

- Use Jenkins to build a Java Hello World app using Maven
- Learn Jenkins freestyle jobs, tool configuration, and Maven lifecycle
- Capture the full CI flow from code to build

---

## 🧰 Tools & Technologies

- Java 21
- Maven 3.9.6
- Jenkins (via Docker)
- Git + GitHub (for repo hosting)

---

## 📁 Project Structure

jenkins-maven-hello/ ├── pom.xml └── src/ └── main/ └── java/ └── HelloWorld.java

yaml
Copy
Edit

---

## 📜 Java Code

### `HelloWorld.java`
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Jenkins + Maven!");
    }
}
⚙️ Maven Configuration
pom.xml
xml
Copy
Edit
<project>
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.example</groupId>
    <artifactId>hello</artifactId>
    <version>1.0</version>
    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.1</version>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>
🚀 Jenkins Setup Steps
Ran Jenkins in Docker:

bash
Copy
Edit
docker run -p 8081:8080 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts
Unlocked Jenkins and installed suggested plugins

Configured JDK and Maven under Global Tool Configuration

Created a Freestyle Job:

Build step: Invoke top-level Maven targets

Goal: clean package

✅ Build Output
Job built successfully using Jenkins + Maven

Console output showed:

csharp
Copy
Edit
[INFO] BUILD SUCCESS
📸 Screenshots
Place them in a screenshots/ folder in the repo

Jenkins Home Dashboard

Global Tool Configuration showing JDK and Maven setup

Freestyle job configuration (Build step with clean package)

Build history with green check

Console Output showing BUILD SUCCESS

🧠 What I Learned
How to run Jenkins via Docker

How to configure build tools (JDK & Maven) in Jenkins

How to create and run a Freestyle CI job

Maven lifecycle basics: clean, compile, package

🔗 Related
Jenkins Official Docs

Maven Official Site
