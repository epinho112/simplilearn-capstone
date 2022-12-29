import groovy.json.JsonSlurper
pipeline {
    agent any
    stages {
        stage('1 - Stop Running instances') { 
            steps {
                script{
                    sh 'docker stop $(docker ps -q)'
                }
            }
        }
        stage('2 - Docker Tests') { 
            steps {
                script{
                    sh 'docker build -t java-docker --target test  .'
                }
            }
        }
        stage('3 - Build Production Image') { 
            steps {
                 sh 'docker build -t java-docker --target production .'
            }
        }
        stage('4 - Upload to DockerHub') { 
            steps {
                 sh 'docker build -t java-docker --target production .'
            }
        }
    }
}
