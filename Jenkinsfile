pipeline{
  agent any
  stages{
  stage('Build'){
    steps{
      build 'PES2UG21CS596-1'
      sh 'g++ working.cpp -o output'
      echo 'Build Stage Successful'
    }
  }
  stage('Test'){
    steps{
      sh './output'
      echo 'Test Stage Successful'
    }
  }
  stage('Deploy'){
    steps {$$$
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
