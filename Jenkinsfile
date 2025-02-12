pipeline {
    agent any
    environment {
        // Use PATH+EXTRA to append to PATH properly
        PATH = "/usr/bin:/bin:/opt/homebrew/bin"
    }
    stages {

        stage('pull') {
            steps {
                git branch: 'main', url: 'https://github.com/PraveenKuber/Amazon-Jenkins.git'
            }
        }
        stage('compile') {
            steps {
                bat 'mvn compile'
            }
        }
        stage('test') {
            steps {
                bat 'mvn test'
                
            }
        }
    
        
        stage('build') {
            steps {
                 bat 'mvn clean install'
            }
        }

        
    }

  post {
    success {
        bat 'echo Build success'
    }
    failure {
        bat 'echo Failure in the build'
    }
}
}
