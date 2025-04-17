pipeline {
    agent any

    environment {
        NODE_HOME = '/usr/local/bin'
        PATH = "$NODE_HOME:$PATH"
    }

    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Installing dependencies using npm
                    sh 'npm install'
                }
            }
        }

        stage('Run Node.js App') {
            steps {
                script {
                    // Running the app in the background
                    sh '''
                        nohup node index.js > app.log 2>&1 &
                        echo "App running at http://localhost:3000"
                    '''
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed!'
        }
    }
}
