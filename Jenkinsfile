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
                bat '"mvn compile"'
            }
        }
        stage('test') {
            steps {
                bat '"mvn test"'
            }
        }
        stage('build') {
            steps {
                bat '"mvn clean install"'
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
}
