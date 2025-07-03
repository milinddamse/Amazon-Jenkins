pipeline {
    agent { label 'windows' }
    environment {
        // Use PATH+EXTRA to append to PATH properly
        PATH = "/usr/bin:/bin:/opt/homebrew/bin"
    }
    stages {

        stage('pull scm') {
            steps {
                git branch: 'main', url: 'https://github.com/milinddamse/Amazon-Jenkins.git'
            }
        }
        stage('compile') {
            steps {
                bat 'mvn compile'
            }
        }

        stage('build') {
            steps {
                 bat 'mvn clean install'
            }
        }

        
    }

  post{

  success{
     echo 'Build success'
  }
    
  failure{
       echo 'Failure in the build'
   }

  }


}
