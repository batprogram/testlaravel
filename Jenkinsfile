pipeline {
    agent any

    environment {
        APP_ENV = 'local'
        DB_CONNECTION = 'mysql'
        DB_DATABASE= 'testlaravel'
    }

    stages {
        stage('Checkout') {
            steps {
                bat 'git clone https://your-repo-url.git' // Ganti dengan URL repository Anda
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'composer install'
            }
        }

        stage('Run Tests') {
            steps {
                bat '.\\vendor\\bin\\phpunit' // Path sesuaikan dengan proyek Anda
            }
        }
    }

    post {
        always {
            junit 'tests/logs/junit.xml'
        }
    }
}
