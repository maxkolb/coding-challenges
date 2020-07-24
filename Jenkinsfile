pipeline {
  agent any
  stages {
    stage('build') {
      if (env.BRANCH_NAME == 'master') {
        steps {
          echo 'master'
        }
      } else if (env.BRANCH_NAME == 'jenkins') {
        steps {
          echo 'jenkins'
        }
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
