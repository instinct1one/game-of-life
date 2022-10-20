pipeline {
    agent { label 'OPEN-JDK8' }
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
        }
        stage('Publish') {
            steps {
                archiveArtifacts artifacts: '**/*.jar'
            }
            post {
                success {
                    junit '**/surefire-reports/**/*.xml'
                 }
            
                }
            }  
        }
    }