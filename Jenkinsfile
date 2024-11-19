@Library("shared-library@DevOps") _

pipeline {
    agent {label 'dev-server-agent'}

    stages {
        stage('Checkout code') {
            steps {
                codeCheckout('dev', 'https://github.com/PakeezaPakeeza/java_springboot_app_CICD.git')
            }
        }
        stage('build') {
            steps {
                buildImage("springboot-application")
            }
        }
        stage('Push Image') {
            steps {
                pushImage("springboot-application")
            }
        }
        stage('Deploy'){
            steps{
                deploy()
            }
        }
        
    }
}

