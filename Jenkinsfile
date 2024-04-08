pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Clona el repositorio de Git donde está tu código fuente
                git 'https://github.com/Kidbuut/nodejs-helloworld-api.git'
            }
        }
        stage('Install dependencies') {
            steps {
                // Instala las dependencias del proyecto
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                // Construye la aplicación (aquí suponemos que hay un script 'build' en package.json)
                sh 'npm run build'
            }
        }
        stage('Test') {
            steps {
                // Ejecuta las pruebas del proyecto (aquí suponemos que hay un script 'test' en package.json)
                sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                // Despliega la aplicación (aquí suponemos que hay un script 'deploy' en package.json)
                sh 'npm run deploy'
            }
        }
    }
    
}
