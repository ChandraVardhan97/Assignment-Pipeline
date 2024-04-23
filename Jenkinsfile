pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')  // Poll SCM every minute for changes
    }

    stages {
        stage('Checkout') {
            steps {
                checkout(
                    $class: 'GitSCM',
                    branches: [[name: '*/main']], // Check out the 'main' branch
                    userRemoteConfigs: [[url: 'https://github.com/ChandraVardhan97/Assignment-Pipeline']] 
                )
            }
        }

        stage('Build') {
            steps {
                sh '/c/Users/chand/AppData/Local/Microsoft/WindowsApps/python3 --version'  // Check Python version
            }
        }

        stage('Test') {
            steps {
                sh 'python main.py'  // Run your Python program
            }
        }
    }
}
