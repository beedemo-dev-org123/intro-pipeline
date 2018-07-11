pipeline {
  agent any
  stages {
    stage('Say Hello') {
      steps {
        echo "Hello ${MY_NAME}!"
        sh 'java -version'
        echo '"$TEST_USER_USR : $TEST_USER_PWD"'
      }
    }
  }
  environment {
    MY_NAME = 'Joe'
    TEST_USER = credentials('test-user')
  }
}