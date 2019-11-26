Jenkinsfile
pipeline {
    agent none
    stages {
        stage('BuildAndTest') {
            agent any
            stages {
                stage('Build') {
                    steps {
                        echo 'Do Build'
                    }
                }
                stage('Test') {
                    steps {
                        echo 'Do Test'
                    }
                }
            }
        }
    }
}


