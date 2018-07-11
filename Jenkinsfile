pipeline {
  agent any
  libraries {
    lib('')
  }
  stages {
    stage('Say Hello') {
      steps {
        echo "Hello ${params.Name}!"
        sh 'java -version'
      }
    }
    stage('Get Kernel') {
      steps {
        script {
          try {
            KERNEL_VERSION = sh (script: "uname -r", returnStdout: true)
          } catch(err) {
            echo "CAUGHT ERROR: ${err}"
            throw err
          }
        }

      }
    }
    stage('Checkpoint') {
      steps {
        echo "${KERNEL_VERSION}"
      }
    }
    stage('Say Kernel') {
      steps {
        echo "${KERNEL_VERSION}"
      }
    }
  }
  environment {
    MY_NAME = 'Joe'
  }
  post {
    aborted {
      echo 'Why didn\'t you push my button?'

    }

  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}