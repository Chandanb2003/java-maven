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
      def tomcatUrl = "http://admin:adminpassword@35.225.1.252:8080/manager/text/deploy?path=/simple-java-maven-app&update=true"
      sh "curl -T target/simple-java-maven-app.war \"${tomcatUrl}\""
    }
  }
}
  }
}
