pipeline {
    agent none
    stages {
        stage('BuildAndTest') {
            matrix {
                agent {
                    dockerfile {
                        filename "${PLATFORM}"
                        label 'linux && docker'
                    }
                }
                axes {
                    axis {
                        name 'PLATFORM'
                        values 'ci/jenkins/docker/centos6/Dockerfile', 'ci/jenkins/docker/centos7/Dockerfile', "ci/jenkins/docker/centos8/Dockerfile", "ci/jenkins/docker/fedora31/Dockerfile", "ci/jenkins/docker/ubuntu1604/Dockerfile" ,"ci/jenkins/docker/ubuntu1804/Dockerfile"
//                        values 'ubuntu:16.04', 'ubuntu:18.04', "centos:6", "centos:7", "centos:8" ,"fedora:31"
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
