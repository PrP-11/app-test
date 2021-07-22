pipeline {
    agent any

    tools {nodejs "node"}

    stages {
        stage("Build") {
            steps {
                sh "npm install"

                sh "npm run build"

                echo "build successful"
            }
        }

        stage("S3 Sync") {
            steps{
                withAWS(credentials: 'Praduman_Pannu', region: 'us-east-1'){
                    sh "aws s3 sync build/ s3://batch4frontend"
                }
            }
        }
    }
}
