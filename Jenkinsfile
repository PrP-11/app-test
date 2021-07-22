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
    }
}