pipeline {
    agent any
    environment {
        GITNAME = '201904202'
        GITMAIL = 'alstmd1017k@gmail.com'
        GITWEBADD = 'https://github.com/201904202/fast-code1.git'
        GITSSH = 'git@github.com:201904202/fast-code1.git'
        GITCREDENTIAL = 'git_cre'
        DOCKERHUB = 'alstmd1017/fast'
        DOCKERHUBCREDENTIAL = 'docker_cre'
    }
    stages {
        stage('Checkout Github') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [],
                userRemoteConfigs: [[credentialsId: GITCREDENTIAL, url: GITWEBADD]]])
            }
            post {
                failure {
                    sh "echo clone failed"
                }
                success {
                    sh "echo clone success"
                }
            }
        }
    }

    stages {
        stage('docker image build') {
            steps {
                sh "docker build -t ${DOCKERHUB}:${currentBuild.number} ."
                sh "docker build -t ${DOCKERHUB}:latest ."
            }
            post {
                failure {
                    sh "echo image build failed"
                }
                success {
                    sh "echo image build success"
                }
            }
        }
    }


    stages {
        stage('start2') {
            steps {
                sh "echo hello jenkins!!!"
            }
            post {
                failure {
                    sh "echo failed"
                }
                success {
                    sh "echo success"
                }
            }
        }
    }

    stages {
        stage('start3') {
            steps {
                sh "echo hello jenkins!!!"
            }
            post {
                failure {
                    sh "echo failed"
                }
                success {
                    sh "echo success"
                }
            }
        }
    }
}