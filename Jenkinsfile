pipeline {
  agent any
  tools { 
      maven 'maven3.9.9' 
      jdk 'jdk1.8' 
  }
  stages {
    stage('Git Bisect') {
      steps {
        script {
          sh "git bisect start 198644632661c67b6c32f59e9047c11a70685e15 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5"
          sh "git bisect run mvn clean test"
          sh "git bisect reset"
        }
      }
    }
  }
}
