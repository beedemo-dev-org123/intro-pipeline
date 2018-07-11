pipeline {
  agent any
  stages {
    stage('Say Hello') {
      steps {
        echo "Hello ${MY_NAME}!"
        sh 'java -version'
        sh '''echo "$TEST_USER_USR"
echo "$TEST_USER_PWD"'''
      }
    }
  }
  environment {
    MY_NAME = 'Joe'
    TEST_USER = credentials('test-user')
  }
}