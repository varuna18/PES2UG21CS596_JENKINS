pipeline{
  agent any
  stages{
  stages('Build'){
    steps{
      sh 'mvn clean install'
      echo 'Buils Stage Successful'
    }
  }
  stage ('Test'){
    steps{
      sh 'mvn test'
      echo 'Test Stage Successful'
      post{
        always{
          junit 'target/surefire-reports/*.xml'
        }
      }
    }
  }
  stage ('Deploy'){
    steps {
      sh 'mvn deploy'
      echo 'Deployment Successful'
    }
  }
}
post{
  failure{
    echo 'Pipeline failed'
  }
}
}

      
