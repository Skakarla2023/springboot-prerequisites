# pom.xml

- pom stands for Project Object model.
- It is the core configuration file for any **Apache Maven-based project**.
- It is a single source of truth that tells Maven how to manage `dependencies`, run tests, compile code and package your appllication.
- Instead of downloading and handling JAR files by yourself, you just declare what you want in `pom.xml` and Maven automates the rest.
- Maven is a build automation tool, that automates the process of building, organizing and managing Java projects.
- `pom.xml` : it is the instruction set or configuration given to Maven.

## Elements in `pom.xml`

### 1. `<project>`

- It is the root element of `pom.xml` file.
- It is the main element, that contains all other elements in it.
- Everything in `pom.xml` is written inside this `<project>` tag.


### 2. `<modelVersion>`

- It defines the version of pom model specification.
- `pom model specification` : It is the blueprint or schema that defines the structural format of a pom.xml file.
- ALmost always `4.0.0`.

### 3. `<parent>`

- It specifies the name of the parent pom, from which the current project can get common configurations.
- **Parent POM** : A `pom.xml` file that provides common settings to other projects.
- It avoids writing same configuration again in every project.

### 4. `<groupId>`

- It identifies the group or organization that owns the project.
- Usually written in a domain-style name, such as `com.example`, like `com.skakarla.xxx.xx`.
- It helps Maven uniquelt identify the project.

### 5. `artifactId>`

- It identifies the specific project within the `groupId`.
- It is usually the name of your application, such as `com.skakarla.ems`.
- It is also commonly used as part of the name of the generated JAR/WAR file.

### 6. `<dependency>`

- It defines one library that your project needs.
- It usually specifies the library's groupId, artifactId, and version.
- Maven uses this information to find and add the library to your project.

### 7. `<dependencies>`

- It contains the libraries that your project needs.
- **Library** : pre-written code that you can use in your application instead of writing everything yourself.
- For example you can use SpringWeb or PostgreSQl as dependencies.

### 8. `<properties>`

- It stores reusable values that can be used in different places in the POM.
- It is commonly used to define Java or dependency versions.
- This helps you avoid writing the same value multiple times.

### 9. `<version>`

- It specifies the current version of your project.
- Examples: 1.0.0, 2.0.0, 1.0.0-SNAPSHOT.
- SNAPSHOT means the project is still under development.

### 10. `<build>`

- It contains settings related to how Maven builds your project.
- **Build**: The process of compiling, testing, and packaging your application.
- It commonly contains <plugins>.

### 11. `<plugins>`

- It contains the Maven plugins used during the build process.
- Plugin: A tool that Maven uses to perform a particular task.
- For example, a plugin can compile Java code or create a JAR file.


### 12. `<plugin>`

- It defines one particular Maven plugin.
- For example, maven-compiler-plugin can be used to configure Java compilation.
- **Compilation**: Converting Java source code into code that the JVM can execute.


### 13. `<name>`

- It specifies the readable name of the project.
- Example: Employee Management System.
- Mainly useful for displaying project information.

### 14. `<description>`

- It gives a short description of what the project does.
- It is mainly useful for documentation and understanding the project.
- It is optional.


### 15. `<url>`

- It specifies the website URL of the project.
- **URL**: The address used to locate something on the internet.
- It is mostly useful for public or open-source projects.


### 16. `<modules>`

- It is used in a parent POM to list the modules belonging to the project.
- **Module**: A separate sub-project that is part of a larger project.
- It allows Maven to build multiple related projects together.

### 17. `<module>`

- It specifies one particular module inside <modules>.
- Usually, it points to a folder containing another pom.xml.
- Example: <module>user-service</module>.


### 18. `<dependencyManagement>`

- It is used to centrally manage dependency versions.
- It is especially useful when multiple modules use the same dependencies.
- Important: It does not add the dependency itself; it mainly tells Maven which version to use.

### 19. `<dependency>` (inside <dependencyManagement>)

- It specifies the version/configuration that should be used for a dependency.
- Child projects can use that dependency without specifying its version again.
- This helps keep dependency versions consistent.

### 20. `<repositories>`

- It tells Maven where it can find and download dependencies.
- **Repository**: A location where Maven libraries are stored.
- Maven Central is the main default repository, so this tag is often unnecessary.

### 21. `<distributionManagement>`

- It tells Maven where to upload/deploy your project's artifact.
- **Deploy**: Uploading the generated project file, such as a JAR, to a remote repository.
- Think: <repositories> = **download from**; <distributionManagement> = **upload to**.


