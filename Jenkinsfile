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
                    }
                }
                stages {
                    stage('Build') {
                        steps {
                            cmakeBuild buildDir: 'build', installation: 'InSearchPath', steps: [[withCmake: true]]
                        }
                    }
                }
            }
        }
    }
}
