pipeline {
    agent any

    stages {

        stage('Build & Test') {
            steps {
                sh '''
                    cd /home/user/calculator-app
                    mvn clean test
                '''
            }
        }

        stage('Package') {
            steps {
                sh '''
                    cd /home/user/calculator-app
                    mvn package
                    cp target/*.jar $WORKSPACE/
                '''
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: '*.jar'
        }
    }
}
