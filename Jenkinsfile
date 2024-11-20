@Library('Shared')_
pipeline{
    agent { label 'dev-worker-node'}
    
    stages{
        stage("Code clone"){
            steps{
                sh "whoami"
            clone("https://github.com/PakeezaPakeeza/java_springboot_app_CICD.git","main")
            }
        }
        stage("Code Build"){
            steps{
            dockerbuild("javaSpringBoot-bankApp","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("dockerHubCreds","javaSpringBoot-bankApp","latest")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}

