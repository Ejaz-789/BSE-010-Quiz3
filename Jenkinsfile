// pipeline {
//     agent any
    
//     stages {
//         stage('Checkout') {
//             steps {
//                 echo 'Checking out code from python branch...'
//                 git branch: 'python', 
//                     url: 'https://github.com/Ejaz-789/BSE-010-Quiz3.git'
//             }
//         }
        
//         stage('Setup Python Environment') {
//             steps {
//                 echo 'Setting up Python environment...'
//                 bat 'D:\\python.exe --version'
//                 // Comment out pip check for now
//                 // bat 'D:\\python.exe -m pip --version'
//                 echo 'Python 3.14.0 detected (pip check skipped)'
//             }
//         }
        
//         stage('Run Python Program') {
//             steps {
//                 echo 'Executing Python program...'
//                 bat 'D:\\python.exe hello.py'
//             }
//         }
        
//         stage('Run Tests') {
//             steps {
//                 echo 'Running additional checks...'
//                 bat 'D:\\python.exe -m py_compile hello.py'
//                 echo 'Python syntax check passed!'
//             }
//         }
//     }
    
//     post {
//         success {
//             echo 'Pipeline executed successfully for python branch!'
//         }
//         failure {
//             echo 'Pipeline failed for python branch!'
//         }
//     }
// }


pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code from python branch...'
                checkout scm  // Best for multibranch pipeline — automatically checks out the correct branch
            }
        }

        stage('Setup Python Environment') {
            steps {
                echo 'Setting up Python environment...'
                sh 'python3 --version'
                sh 'python3 -m pip --version || true'  // Optional: check pip (|| true to avoid failure if missing)
                echo 'Python environment ready'
            }
        }

        stage('Run Python Program') {
            steps {
                echo 'Executing Python program...'
                sh 'python3 hello.py'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running syntax check...'
                sh 'python3 -m py_compile hello.py'
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
