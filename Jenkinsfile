pipeline {
    agent none
    stages {
        stage('BuildAndTest') {
            matrix {
                agent any
                axes {
                    axis {
                        name 'PLATFORM'
                        values 'ubuntu'
                    }
                }
                stages {

                    stage('Build') {
                        agent {
                            docker {
                                image "${PLATFORM}"
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
