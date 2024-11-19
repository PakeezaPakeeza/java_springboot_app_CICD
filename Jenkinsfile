@Library("shared")_

pipeline {
    agent {label 'dev-server-agent'}

    stages {
        stage('Checkout code') {
            steps {
                clone('main', 'https://github.com/PakeezaPakeeza/java_springboot_app_CICD.git')
            }
        }
        stage('build') {
            steps {
                dockerbuild("springboot-application")
            }
        }
        stage('Push Image') {
            steps {
                dockerpush("dockerHubCreds","notes-app","latest")
            }
        }
        stage('Deploy'){
            steps{
                deploy()
            }
        }
        
    }
}

