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
                bat 'python --version'
                bat 'pip --version'
            }
        }
        
        stage('Run Python Program') {
            steps {
                echo 'Executing Python program...'
                bat 'python hello.py'  // Make sure this matches your file name
            }
        }
        
        stage('Run Tests') {
            steps {
                echo 'Running additional checks...'
                bat 'python -m py_compile hello.py'
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
