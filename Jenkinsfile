@Library('shared')_

pipeline {
    agent {label 'dev-server-agent'}

    stages {
        stage('Checkout code') {
            steps {
                clone("https://github.com/PakeezaPakeeza/java_springboot_app_CICD.git","main")
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

