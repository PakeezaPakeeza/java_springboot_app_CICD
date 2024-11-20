@Library('Shared')_
pipeline{
    agent { label 'dev-worker-node'}
    environment {
        COMPOSE_PROJECT_NAME = "bankapp_${env.BRANCH_NAME ?: 'main'}_${BUILD_NUMBER}" // Unique project name
    }
    stages{
        stage("Code clone"){
            steps{
                sh "whoami"
            clone("https://github.com/PakeezaPakeeza/java_springboot_app_CICD.git","main")
            }
        }
        stage("Code Build"){
            steps{
            dockerbuild("javaspringboot-bankapp","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("dockerHubCreds","javaspringboot-bankapp","latest")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}

