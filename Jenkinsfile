// pipeline {
//     agent any
    
//     stages {
//         stage('Checkout') {
//             steps {
//                 echo 'Checking out code from main branch...'
//                 git branch: 'main', 
//                     url: 'https://github.com/Ejaz-789/BSE-010-Quiz3.git'
//             }
//         }
        
//         stage('Compile Java') {
//             steps {
//                 echo 'Compiling Java program...'
//                 bat 'javac Hello.java'  // Changed to Hello.java
//             }
//         }
        
//         stage('Run Java') {
//             steps {
//                 echo 'Running Java program...'
//                 bat 'java Hello'  // Changed to Hello (no .java extension)
//             }
//         }
        
//         stage('Archive Artifacts') {
//             steps {
//                 echo 'Archiving generated artifacts...'
//                 archiveArtifacts artifacts: '*.class', fingerprint: true
//             }
//         }
//     }
    
//     post {
//         success {
//             echo 'Pipeline executed successfully for main branch!'
//         }
//         failure {
//             echo 'Pipeline failed for main branch!'
//         }
//     }
// }


pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code from main branch...'
                checkout scm
            }
        }

        stage('Compile Java') {
            steps {
                echo 'Compiling Java program...'
                sh 'javac Hello.java'   // ← Use sh instead of bat
            }
        }

        stage('Run Java') {
            steps {
                echo 'Running Java program...'
                sh 'java Hello'         // ← Change this too (no .class needed)
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: '*.class', allowEmptyArchive: true
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed for main branch!'
        }
        success {
            echo 'Pipeline succeeded!'
        }
    }
}
