pipeline {
    agent { label 'OPEN-JDK8' }
    tools {
        maven 'MVN-3.6'
        jdk 'OPENJDK-8'
    }
    stages {
        stage('Clone Repo') {
            steps {
                git url: "https://github.com/instinct1one/game-of-life.git", 
                branch: "master"
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
            post {
                always {
                    junit '**/surefire-reports/**/*.xml' 
                }
        }
    }
}
}