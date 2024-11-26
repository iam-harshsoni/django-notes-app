@Library("Shared") _
pipeline{
    agent { label "vinod" }
    
    stages{
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        
        stage("Code"){
            steps{
                code("https://github.com/iam-harshsoni/django-notes-app","main")
            }
        }
        
        stage("Build"){
            steps{
                docker_build("notes-app","latest","harshsoni777")
            }
        }
        
        stage("Push to DockerHub"){
            steps{
                docker_push("notes-app","latest","harshsoni777")
            }
        }
        
        stage("Test"){
            steps{
                echo "This is Test Stage"
            }
        }
        
        stage("Deploy"){
            steps{
                script{
                    echo "This is just to see demo"
                    docker_compose()
                }
            }
        }
    }
}
