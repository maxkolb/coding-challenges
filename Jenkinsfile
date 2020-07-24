pipeline {
  agent any
  stages {
    stage('build:master') {
      when {
        branch 'master'
      }
      steps {
        echo 'master'
      }
    }
    stage('build:jenkins') {
      when {
        branch 'jenkins'
      }
      steps {
        echo 'jenkins'
      }
    }

    stage('test') {
      parallel {
        stage('test:license') {
          steps {
            echo 'license'
          }
        }

        stage('test:unit') {
          steps {
            echo 'unit'
          }
        }

      }
    }

    stage('analyze:sonarqube') {
      steps {
        echo 'sonar'
      }
    }

    stage('terraform:apply') {
      steps {
        echo 'terraform'
      }
    }

    stage('deploy') {
      steps {
        echo 'deploy'
      }
    }

  }
}
