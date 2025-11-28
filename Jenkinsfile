pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Aucune compilation nécessaire pour un site HTML.'
            }
        }

        stage('Deploy to local Windows folder') {
            steps {
                script {
                    echo "Déploiement dans C:/deploy-site/site"
                }
                bat """
                cd C:\\deploy-site\\site
                git pull
                git config --global --add safe.directory
                """
            }
        }
    }

    post {
        success {
            echo 'Déploiement réussi !'
        }
        failure {
            echo 'Erreur dans le pipeline.'
        }
    }
}
