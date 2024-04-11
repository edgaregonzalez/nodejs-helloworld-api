pipeline {
    agent any
    
    stages {
        stage('Buil') {
            steps {
                // Ejecuta el comando npm install para instalar las dependencias
                sh 'npm install'
            }
        }
        
        stage('Test') {
            steps {
                // Ejecuta el comando npm test para ejecutar las pruebas
                sh 'npm test'
            }
        }
    }
    
    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}