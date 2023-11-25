pipeline {
    agent any
    environment {
        name = 'Akshay'
    }
    parameters {
        string(name: 'person', defaultValue: 'Akshay Deshpande', description: 'Who are you?')
        booleanParam(name: 'isMale', defaultValue: true, description: '')
        choice(name: 'City', choices: ['Pune', 'Blore', 'Goa'], description: '')
    }
    stages {
        stage('Running date command') {
            steps {
                sh '''
                ls 
                date 
                pwd
                cal 2023
                '''
            }
        }

        stage('Environment variables') {
            environment {
                username = 'Akshay1'
            }
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${person}"'
            }
        }

        stage('Parameters') {
            steps {
                echo 'Deploy on test'
                sh 'echo "${username}"'
            }
        }

        stage('Continue?') {
            input {
                message "Should we continue"
                ok "Yes we should"
            }
            steps {
                echo 'deploy on prod'
            }
        }

        stage('Deploy on prod') {
            steps {
                echo 'deploy on prod'
            }
        }
    }

    post {
        always {
            echo 'I will always say Hello again!'
        }
        failure{
            echo 'Failure'
        }
        success{
            echo 'Success'
        }
    }
}
