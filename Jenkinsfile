pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/CodeByVar/Demo-Serenity-Cucumber.git'
            }
        }

        stage('Build & Test') {
            steps {
                // **DEBES ASEGURARTE DE USAR withMaven**
                // Cambia 'M3' por el nombre exacto de la configuración de Maven en Jenkins.
                withMaven(maven: 'M3') {
                    bat 'mvn clean verify'
                }
            }
        }

        stage('Report') {
            steps {
                publishHTML([reportDir: 'target/site/serenity', reportFiles: 'index.html', reportName: 'Serenity Report'])
            }
        }
    }
}
