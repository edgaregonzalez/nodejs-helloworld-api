pipeline {
    agent any 
    tools {
        nodejs 'nodejs'
    }
    stages {
        stage('Build') {
            steps {
                echo "Ejecutar NPM install"
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo "Ejecutar NPM Test push"
                sh 'npm test'
            }
        }

    }


}
         