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
                  sh "aws s3 sync build/ s3://batch4frontend"
            }
        }
    }
}
