pipeline{
    agent {
        docker{
            image 'qaninja/rubywd'
        }
    }
    
    stages{
        stage('biuld'){
            steps {
                echo 'building or resolve dependencies'
                sh 'rm -f Gemfile.lock'
                sh 'bundle install'
            }
        }
        stage('test'){
            steps {
                echo 'running regression teste'
                sh 'bundle exec cucumber -p ci'
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