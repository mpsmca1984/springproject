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
      build 'pipelinetest'
    }
    stage('Test app'){
      echo 'Testing is stated!'    
    }
    stage('Run'){
     echo 'Running!'
      steps{
    	sh 'cd /Users/mritunjaysingh/.jenkins/workspace/app-test/src/springproject'
        sh 'javac Jenkintest.java'
        sh  'cd ..'
        sh 'java springproject.Jenkintest'
    }
    }
  }
}