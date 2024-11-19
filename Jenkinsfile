@Library('shared')_

pipeline {
    agent {label 'dev-server-agent'}

    stages {
        stage('Checkout code') {
            steps {
                clone("https://github.com/LondheShubham153/django-notes-app.git","main")
            }
        }
        stage('build') {
            steps {
                dockerbuild("springboot-application","latest")
            }
        }
        stage('Push Image') {
            steps {
                dockerpush("dockerHubCreds","springboot-application","latest")
            }
        }
        stage('Deploy'){
            steps{
                deploy()
            }
        }
        
    }
}

