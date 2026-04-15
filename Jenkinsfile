pipeline {
    agent any
    stages {
        stage('Clonar Código') {
            steps {
                checkout scm
            }
        }
        stage('Análisis y Quality Gate (Aduana)') {
            steps {
                script {
                    // 1. Llamamos a la herramienta instalada en el Paso 14
                    def scannerHome = tool 'sonar-scanner'
                    
                    // 2. Usamos la conexión a SonarCloud creada en el Paso 13
                    withSonarQubeEnv('SonarCloud') {
                        // 3. Ejecutamos el análisis. El "wait=true" es el bloqueo automático.
                        sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=LuisMallma_examen-devops-sonarqube -Dsonar.organization=luismallma -Dsonar.host.url=https://sonarcloud.io -Dsonar.qualitygate.wait=true"
                    }
                }
            }
        }
        stage('Despliegue a Producción') {
            steps {
                echo "✅ ¡ÉXITO! El código es limpio y pasó el Quality Gate."
                echo "Iniciando despliegue de infraestructura inmutable..."
            }
        }
    }
}