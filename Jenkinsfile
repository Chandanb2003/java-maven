pipeline {
  agent { label 'slave1' }
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
    stage('Deploy to Tomcat') {
      steps {
        script {
          def tomcatUrl = "http://deploy:deploypassword@35.225.1.252:8081/manager/text/deploy?path=/simple-java-maven-app&update=true"
          sh "curl -T target/simple-java-maven-app-1.0-SNAPSHOT.war \"${tomcatUrl}\""
        }
      }
    }
  }
}
