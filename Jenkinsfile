pipeline {
    agent any

    stages {
        stage('Параллельный запуск') {
            parallel {
                stage('Ветка Pipeline-A') {
                    steps {
                        echo 'Запуск pipeline api-test'
                        build job: 'api-test', wait: true
                    }
                }
                stage('Ветка Pipeline-B') {
                    steps {
                        echo 'Запуск pipeline playwright-test'
                        build job: 'playwright-test', wait: true
                    }
                }
            }
        }
    }
}