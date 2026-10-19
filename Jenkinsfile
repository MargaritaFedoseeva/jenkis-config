pipeline {
    agent any

    stages {
        stage('Параллельный запуск') {
            parallel {
                stage('Pipeline api-test') {
                    steps {
                        echo 'Запуск pipeline api-test'
                        build job: 'api-test', wait: true, propagate: false, parameters: [string(name: 'BRANCH', value: params.API_BRANCH)]
                    }
                }
                stage('Pipeline playwright-test') {
                    steps {
                        echo 'Запуск pipeline playwright-test'
                        build job: 'playwright-test', wait: true, propagate: false, parameters: [string(name: 'BRANCH', value: params.PLAYWRIGHT_BRANCH)]
                    }
                }
            }
        }
    }
}