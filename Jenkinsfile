pipeline {
    agent any
    stages {
        stage('Clonar Código') {
            steps {
                checkout scm
            }
        }
        stage('Análisis de SonarCloud') {
            steps {
                echo "Enviando código a SonarCloud..."
                
            }
        }
        stage('Quality Gate Check') {
            steps {
                echo "Revisando si la aduana permite pasar el código..."
                
            }
        }
    }
}