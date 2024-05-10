pipeline {
   agent any
   stages {
      stage('Prepare Environment') {
            steps {
                script {
                  bat "python -m venv venv"
                  bat "venv\\Scripts\\activate"
                  bat "pip install --upgrade pip"
                  bat "pip install -r requirements.txt"
                  echo 'Setting up a clean virtual environment'
                }
            }
      }

      stage('Run Test') {
         steps {
            browserstack(credentialsId: 'c567963d-060b-4e14-bdba-b6921312361b') {
               script {
                  bat "venv\\Scripts\\activate"
                  bat "browserstack-sdk pytest -s .\\tests\\test_browserstack.py"
               }
            }
         }
      }
    }
    post {
        always {
            echo 'Cleaning up environment'
            // Clean up the workspace to ensure no data persists between builds
            cleanWs()
        }
        success {
            echo 'Tests completed successfully.'
        }
        failure {
            echo 'Tests failed. Check the logs for details.'
            // Additional commands can be added here to handle failures, like sending notifications
        }
    }
  }