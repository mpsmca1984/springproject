pipeline{
  agent any
stages{
    stage('GIT checkout'){
      steps{
        checkout([
          $class: 'GitSCM',
          branches: [
            [
              name: '*/master'
            ]
          ],
          userRemoteConfigs: [
            [
              url: 'https://github.com/mpsmca1984/springproject.git'
            ]
          ]
        ])
      }
    }
    stage('build'){
    steps{
      echo 'build is in progress'
      }
    }
    stage('Test app'){
    steps{
      echo 'Testing is stated! have to include'
      }    
    }
    stage('Run'){
    
      steps{
       
       echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
       echo "${env.JENKINS_HOME}/workspace/${env.JOB_NAME}/src/springproject"
       sh  "javac ${env.JENKINS_HOME}/workspace/${env.JOB_NAME}/src/springproject/*.java"
       sh "cd ${env.JENKINS_HOME}/workspace/${env.JOB_NAME}/src"
      }
    }
  }
}
