pipeline{
    agent any

    parameters {
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: '')
        string(name: 'Branch_Name', defaultValue: 'main', description:'enter branch to build')
    }

    stages {
        stage('Hello') {
            steps {
                echo 'hello world'
            }
        }
        stage ('hi') {
            steps{
                echo 'hi'
            }
        }
        stage ('howdy') {
            
            steps{
                echo 'howdy'
            }
        }
        stage ('Git checkout'){
             when {
        expression {
               env.BRANCH_NAME=='main'
         }
       }
            steps {
                git branch: 'feature-Martin2', changelog: false, credentialsId: 'MartinChukwu', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
        stage('List files'){
            steps{
                sh 'ls -lrt'
            }
        }
         stage('env variables') {
    steps{
        sh 'echo $version '
        echo "${env.version}"
        echo "${env.db_name}"

        script {
            print env.version
        }
    }
    }
}
