pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/NiranjanSurve/DO_Practical_4.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Node.js App') {
            steps {
                sh '''
                    nohup node index.js > app.log 2>&1 &
                    echo "App running at http://localhost:3000"
                '''
            }
        }
    }
}
