
pipeline {
    agent any

    tools {
        maven 'MAVEN-HOME'
    }

    stages {
        stage('Git Repo & Clean') {
            steps {
                deleteDir()
                bat 'git clone https://github.com/Chaithanyakk29/E-ticketing.git eticket'
                bat 'mvn clean -f eticket'
                echo "Build Number: ${BUILD_NUMBER}"
            }
        }

        stage('Install') {
            steps {
                bat 'mvn install -f eticket'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test -f eticket'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package -f eticket'
            }
        }
    }
}
