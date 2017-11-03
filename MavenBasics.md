# Maven Overview
- Primary goal of maven
  A comprehensive model for projects, which is reusable, maintainable, and easier to comprehend
  Plugins or tools that interact with this declarative model
- Build lifecycle
  1. prepare-resources	resource copying	Resource copying can be customized in this phase
  2. validate	Validating the information	Validates if the project is correct and if all necessary information is available
  3. compile	compilation	Source code compilation is done in this phase
  4. Test	Testing	Tests the compiled source code suitable for testing framework
  5. package	packaging	This phase creates the JAR/WAR package as mentioned in the packaging in POM.xml
  6. install	installation	This phase installs the package in local/remote maven repository
  7. Deploy	Deploying	Copies the final package to the remote repository
- Plugins
  Build plugins: They execute during the build process and should be configured in the <build/> element of pom.xml
  Reporting plugins: They execute during the site generation process and they should be configured in the <reporting/> element of the pom.xml
