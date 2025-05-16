pipeline {
    agent any

    tools {
        maven 'Maven' 
        jdk 'JDK'         
    }

    environment {
        // Define the path to the JAR file
        JAR_PATH = 'target/MyMavenGuavaApp-1.0-SNAPSHOT.jar'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/bitcse6c/MyMavenGuavaApp.git'

            }
        }

        stage('Build JAR') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Run Application') {
            steps {
                sh 'mvn exec:java -Dexec.mainClass="com.example.App"'
            }
        }
    }

    post {
        success {
            echo 'Build and execution successful!'
        }
        failure {
            echo 'Build or execution failed!'
        }
    }
}
