pipeline {
  agent any
  
  environment {
    FLUTTER_HOME = tool 'Flutter'
    PATH="${FLUTTER_HOME}/bin:${PATH}"
  }

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Build Flutter App') {
      steps {
        sh 'flutter pub get'
        sh 'flutter build web'
      }
    }

    stage('Deploy to GCP') {
      steps {
        sh 'gcloud app deploy --quiet'
      }
    }
  }
}
