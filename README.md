# TeamB_Maven
This repository is a simple Maven project that contains a dependency to the project contained in its sister repo: [TeamA_Maven](https://github.com/rmartinez10x/TeamA_Maven).
 
SOAtest Desktop:
To import the TeamA dependency from TeamB's pom.xml, create the following Eclipse Run Configuration in your SOAtest workspace: 
For the Maven run configuration:
Step 1. Set the Goals to (clean dependency:unpack)
Step 2. Add Parameter with
Name "artifact"
Value "${GroupId}:${ArtifactId}:${Version}:zip"
 
Automation:
Here is how to run the TeamB project as part of automation with the SOAtest Maven Plugin: [SOAtest Maven Plugin](https://parasoft.github.io/soatest-maven-plugin/)

For the Maven run configuration:
Step 1. Set the Goals to (clean dependency:unpack soatest:soatest)

Step 2. Add Parameter with
Name "soatest.home"
Value "Path\To\SOAtest\Installation"
example:C:\Program Files\Parasoft\SOAtest & Virtualize\2024.1

Step 3. Add Parameter with
Name "soatest.config"
Value "builtin://Demo Configuration"

Step 4. Add Parameter with
Name "soatest.report"
Value "target/reports"

Step 5. Add Parameter with
Name "artifact"
Value "${GroupId}:${ArtifactId}:${Version}:zip"