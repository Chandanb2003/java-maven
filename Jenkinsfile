pipeline {
    agent { label 'slave1' } // replace with your slave's label
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Chandanb2003/java-maven.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
