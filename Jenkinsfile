pipeline {
   agent any
   stages {
      stage('setup') {
         steps {
            browserstack(credentialsId: 'c567963d-060b-4e14-bdba-b6921312361b') {
               script {
                  // Setting up virtual environment
                  bat "python -m venv venv"
                  bat "venv\\Scripts\\activate"
                  bat "pip install --upgrade pip"
                  // Installing dependencies
                  bat "pip install -r requirements.txt"
                  // Running the test with BrowserStack SDK
                  bat "browserstack-sdk pytest -s .\\tests\\test_browserstack.py"
               }
            }
         }
      }
    }
  }
