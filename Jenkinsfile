pipeline {
    agent any
    parameters{
    string(name:'Branch_Name', defaultValue: 'main', description: 'enter branch name to build')
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Git Checkout') {
            steps{
            checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '$Branch_Name']], extensions: [], userRemoteConfigs: [[credentialsId: 'yannick-jenkins', url: 'https://github.com/IBT-learning/ibt-maven.git']])
            }
        }
        stage('List files'){
        when{
            expression{
            env.BRANCH_NAME == 'main'
            }
        }
        steps{
          sh 'ls'
          }
        }
    }
}
