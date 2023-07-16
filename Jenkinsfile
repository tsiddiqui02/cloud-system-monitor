pipeline {

    agent any
    environment {
        NEW_VERSION = '1.3.0'
        SERVER_CREDENTIALS = credentials('ts-credentials')
    }
    stages {

        stage("build") {

            steps {
                echo 'building the application...'
                echo "building version ${NEW_VERSION}"
            }
        }
ß
        stage("test") {

            steps {
                echo 'testing the application...'
            }
        }

        stage("deploy") {

            steps {
                echo 'deploying the application...'
                withCredentials([
                    usernamePassword(credentials: 'ts-credentials', usernameVariable: USER, passwordVariable: PWD)
                ]) {
                    sh "some script ${USER} ${PWD}"
                }
            }
        }
    }
}