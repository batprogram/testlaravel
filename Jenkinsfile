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
                at 'git clone https://github.com/batprogram/testlaravel.git' branch: 'main'
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
