pipeline {
   agent any
   stages {
      stage('Prepare Environment') {
         steps {
            script {
               echo 'Setting up a clean virtual environment'
               bat "python -m venv venv"
               bat "venv\\Scripts\\activate"
               bat "pip install --upgrade pip"
               bat "pip install -r requirements.txt"
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
         cleanWs()
      }
      success {
         echo 'Tests completed successfully.'
      }
      failure {
         echo 'Tests failed. Check the logs for details.'
      }
   }
}