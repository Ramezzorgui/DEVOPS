pipeline {
    agent any

    tools {
        maven 'M2_HOME'
    }

    options {
        timeout(time: 10, unit: 'MINUTES') 
    }

    environment {
        APP_ENV = "DEV"
    }

    stages {
        stage('Code Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Ramezzorgui/DEVOPS.git'
            }
        }

        stage('Code Build') {
            steps {
                sh 'mvn clean install -Dmaven.test.skip=true'
            }
        }
    }

    post {
        always {
            echo "====== Always executed ======"
        }
        success {
            echo "===== Pipeline executed successfully ====="
        }
        failure {
            echo "====== Pipeline execution failed ======"
        }
    }
}
