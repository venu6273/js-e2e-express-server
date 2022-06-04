pipeline{
    agent{label ('JDK11')}
    
    triggers{
        cron('H * * * *')
    }
    stages{
        stage('source code'){
            steps{
                git branch: 'main', url: 'https://github.com/venu6273/js-e2e-express-server.git'
            }
        }
        stage('build the code'){
            steps{
                sh '''npm install
                      npm run build
                      npm pack'''

            }
        }
    }   
    post{
        success{
             archive '**/*.tgz'
        }
    
    }
}