pipeline {
    agent any

    parameters {
        string (name: 'Branch_Name' , defaultvalue: 'main', description: 'enter the branch to build')
    }

    stages {
        stage('Hello'){
            steps {
                echo "hello"
            }
        }
        stage('Hi'){
                    steps {
                        echo "Hi"
                    }
                }
        stage ('Git checkout') {
            steps{
                git branch: '%Branch_Name%', changelog: false, credentialsId: 'Github_user_cred_ccjacobs14', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
        stage('list all my files') {
            steps{
            bat 'dir'
            }
        }
    }
}