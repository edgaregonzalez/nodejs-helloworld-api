pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Aquí irían los comandos para construir tu aplicación Node.js
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                // Aquí irían los comandos para ejecutar las pruebas de tu aplicación Node.js
                sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                // Aquí irían los comandos para desplegar tu aplicación Node.js
                // Por ejemplo, puedes usar ssh para conectarte a un servidor remoto y desplegarla
                sh 'ssh user@server "npm deploy"'
            }
        }
    }
}