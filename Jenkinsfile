pipeline{
  agent any
  stages{
  stages('Clone Repository'){
    steps{
      checkout([$class: 'GitSCM',
      branches: [[name: '*/main']],
      userRemoteConfigs: [[URL: 'https://github.com/varuna18/PES2UG21CS596_JENKINS.git']]])
    }
  }
  state ('Build'){
    steps{
      build 'PES2UG21CS596-1'
      sh 'g++ main.cpp -o output'
    }
  }
  stage ('Test'){
    steps{
      sh './output'
      
    }
  }
  stage ('Deploy'){
    steps {
     
      echo 'deploy'
    }
  }
}
post{
  failure{
    echo 'Pipeline failed'
  }
}
                           }

      
