@Library('Shared')_
pipeline{
    agent { label 'dev-server'}
    
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

