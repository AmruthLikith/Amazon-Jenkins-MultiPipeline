
pipeline {
    agent any
    
    stages {

        stage('pull') {
            steps {
                git branch: 'main', url: 'https://github.com/PraveenKuber/Amazon-Jenkins.git'
            }
        }
        stage('compile') {
            steps {
                bat '"C:\\Users\\Amruthesh\\Downloads\\apache-maven-3.9.9\\bin\\mvn" compile'
            }
        }
        stage('test') {
            steps {
               bat '"C:\\Users\\Amruthesh\\Downloads\\apache-maven-3.9.9\\bin\\mvn" test'
            }
        }
        stage('build') {
            steps {
               bat '"C:\\Users\\Amruthesh\\Downloads\\apache-maven-3.9.9\\bin\\mvn" clean install'
            }
        }
    }

    post {
        success {
            bat '"C:\\Windows\\System32\\cmd.exe" /c echo Build success"'
        }
        failure {
            bat '"C:\\Windows\\System32\\cmd.exe" /c echo Failure in the build"'
        }
    } 
}

