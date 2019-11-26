pipeline {
    agent none
    stages {
        stage('BuildAndTest') {
            matrix {
                agent {
                    docker {
                        image "${PLATFORM}"
                        label 'linux && docker'
                    }
                }
                axes {
                    axis {
                        name 'PLATFORM'
                        values 'ubuntu:16.04', 'ubuntu:18.04', "centos:6", "centos:7", "centos:8" ,"fedora:31"
                    }
                }
                stages {

                    stage('Build') {
                        
                        steps {
                            sh "cat /etc/*release"
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
