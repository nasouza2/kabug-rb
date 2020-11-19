pipeline{
    agent {
        docker{
            image 'ruby'
        }
    }
    
    stages{
        stage('biuld'){
            steps {
                sh 'bundle install'
            }
        }
        stage('test'){
            steps {
                echo 'running regression teste'
            }
        }
        stage('uat'){
            steps{
                echo 'wait for user acceptance'
                input(message: 'go to production?', ok: 'yes')
            }
        }
        stage('prod'){
            steps{
                echo 'Webapp is ready :)'
            }
        }
    }
}