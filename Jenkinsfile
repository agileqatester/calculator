pipeline {
   agent any

   tools {
      // Install the Maven version configured as "M3" and add it to the path.
      maven "M3"
   }

   stages {
      stage('Git') {
        steps {
            // Get some code from a GitHub repository
            git 'https://github.com/agileqatester/calculator.git'
        }
      }   
      stage('Build'){
          steps{
            // Run Maven on a Unix agent.
            sh 'mvn -f calculator/pom.xml clean compile'
          }
      }
      stage('Unit Test'){
          steps{
            // Run Maven on a Unix agent.
            sh 'cd calculator;pwd;mvn test'
          }
      }
            // To run Maven on a Windows agent, use
            // bat "mvn -Dmaven.test.failure.ignore=true clean package"
      }
}
