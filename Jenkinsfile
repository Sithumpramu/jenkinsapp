pipeline{
    agent any
    tools{
        nodejs 'node'
    }
    stages{
        stage("npm install"){
            steps{
                bat "npm install"
            }

        }
        stage("npm build"){
            steps{
                bat "npm run build"
            }

        }

        stage("s3 deploy"){
            steps{
                sh "aws s3 sync dist/ s3://jenkins-react-s3 --delete"
            }

        }
    }

}