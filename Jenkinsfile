pipeline {
    agent { label 'slave1' } // replace with your slave's label
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/yourusername/simple-java-maven-app.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
