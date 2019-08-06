pipeline {
    agent none
    stages {
        stage('build frontend') {
            when {
                changeset "frontend/**"
            }
            steps {
                echo 'building frontend app'
            }
        }

        stage('build backend') {
            agent {
                dockerfile {
                    filename 'Dockerfile'
                    dir 'backend/docker'
                }
            }
            when {
                changeset "backend/**"
            }
            steps {
                echo 'building backend app'
            }
        }
    }
}