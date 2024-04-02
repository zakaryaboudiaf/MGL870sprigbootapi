pipeline {
    agent {
        docker {
            image 'gradle:latest' // Utiliser l'image Docker Gradle officielle
            args '-v /root/.gradle:/root/.gradle' // Montage du répertoire Gradle pour la persistance des caches
        }
    }
    
    stages {
        stage('Build') {
            steps {
                sh './gradlew build' // Commande pour construire avec Gradle
            }
        }
        stage('Test') {
            steps {
                sh './gradlew test' // Commande pour exécuter les tests avec Gradle
            }
        }
    }
    
    post {
        success {
            echo 'Build successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
