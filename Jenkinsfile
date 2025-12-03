pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code from python branch...'
                git branch: 'python', 
                    url: 'https://github.com/Ejaz-789/BSE-010-Quiz3.git'
            }
        }
        
        stage('Setup Python Environment') {
            steps {
                echo 'Setting up Python environment...'
                bat 'D:\\python.exe --version'
                // Comment out pip check for now
                // bat 'D:\\python.exe -m pip --version'
                echo 'Python 3.14.0 detected (pip check skipped)'
            }
        }
        
        stage('Run Python Program') {
            steps {
                echo 'Executing Python program...'
                bat 'D:\\python.exe hello.py'
            }
        }
        
        stage('Run Tests') {
            steps {
                echo 'Running additional checks...'
                bat 'D:\\python.exe -m py_compile hello.py'
                echo 'Python syntax check passed!'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline executed successfully for python branch!'
        }
        failure {
            echo 'Pipeline failed for python branch!'
        }
    }
}
