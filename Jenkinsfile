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
                sh '"C:\\Users\\chand\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" --version'  // Check Python version
            }
        }

        stage('Test') {
            steps {
                sh '"C:\\Users\\chand\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" main.py'  // Run your Python program
            }
        }
    }
}
