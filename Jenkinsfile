pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
      }
      post {
        always {
            junit 'target/surefire-reports/*.xml'
          }
       }
    }
    stage('Deploy') {
      steps {
        sh '''echo Deploy steps'''
      }
    }
  }
}
