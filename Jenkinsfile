pipeline {
parameters {
    string(name:'Branch_name', defaultValue:'main', description:'enter your branch name')
}
    agent any
    stages {
        stage ('hello') {
            steps {
                echo "hello world"
            }
        }
         stage ('hi') {
             steps {
                  echo "hi"
             }
         }
         stage ('windows bash cmd') {
            steps {
                sh "pwd"
            }
         }
         stage ('get branchname') {
            steps {
                echo "${params.$Branch_name}"
            }
         }
         stage ('git checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/$Branch_name']], extensions: [], userRemoteConfigs: [[credentialsId: 'git_credential_laura', url: 'https://github.com/IBT-learning/ibt-maven.git']])
            }
         }
    }
}
