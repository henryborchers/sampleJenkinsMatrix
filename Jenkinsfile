pipeline {
    agent none
    stages {
        stage('BuildAndTest') {
            matrix {
                agent any
                axes {
                    axis {
                        name 'PLATFORM'
                        values 'ubuntu:16.04', 'ubuntu:18.04'
                    }
                }
                stages {

                    stage('Build') {
                        agent {
                            docker {
                                image "${PLATFORM}"
                                label 'linux && docker'
                            }
                        }
                        steps {
                            sh "echo \"Do Build for ${PLATFORM}\""
                        }
                    }
                    stage('Test') {
                        steps {
                            echo "Do Test for ${PLATFORM}"
                        }
                    }
                }
            }
        }
    }
}
