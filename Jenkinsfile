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
      echo 'Testing is stated!'
      }    
    }
    stage('Run'){
    
      steps{
       echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
    	sh 'cd /Users/mritunjaysingh/.jenkins/workspace/testapp/src/springproject'
        sh 'javac Jenkintest.java'
        sh  'cd ..'
        sh 'java springproject.Jenkintest'
    }
    }
  }
}