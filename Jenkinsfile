pipeline {
    agent any 

    environment {
        DOCKER_IMAGE = 'mon-conteneur-apache' // Remplace par le nom de ton image Docker Apache
        REPO_URL = 'https://github.com/amsayan/kotranaDocker.git' // Remplace par l'URL de ton dépôt
    }

    stages {
        stage('Checkout') {
            steps {
                // Récupérer le code source de Git
                git branch: 'dev', url: "${REPO_URL}"
            }
        }

        stage('Merge Branches') {
            steps {
                // Fusionner les branches (remplace par tes noms de branches)
                sh 'git checkout main' // Change pour ta branche cible
                sh 'git merge dev' // Change pour ta branche source
            }
        }
    }

    post {
        success {
            echo 'Déploiement réussi !'
        }
        failure {
            echo 'Échec du déploiement.'
        }
    }
}
