pipeline {
    agent any
    stages {
        stage('build frontend') {
            when {
                changeset "**/frontend/*.*"
            }
            steps {
                echo 'building frontend app'
            }
        }

        stage('build backend') {
            when {
                changeset "**/backend/*.*"
            }
            steps {
                echo 'building backend app'
            }
        }
    }
}