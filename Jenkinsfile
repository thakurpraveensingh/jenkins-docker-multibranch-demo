pipeline {
  agent any
  stages {
    stage("build") {
      steps {
        echo "builidng the application with commit pushes"
      }
    }
    
    stage("test") {
      steps {
        echo "testing the application"
      }
    }
    stage("run frontend"){
      steps {
        echo "executing yarn..."
        nodejs("Node-10.17") {
          sh "yarn install"
        }
      }
    }
    stage("run backend"){
      steps {
        echo "executing gradle..."
        withGradle() {
          sh "./gradlew -v"
        }
      }
    }
  }
}
