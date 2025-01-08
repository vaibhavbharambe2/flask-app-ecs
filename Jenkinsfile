@Library("PushImage") _
pipeline{
    
    agent { label 'alex' }
    
    stages{
        
        stage("Code")
        {
            steps
            {
                script
                {
                    clone("https://github.com/vaibhavbharambe2/flask-app-ecs.git","main")
                }
            }
        }
        stage("Build")
        {
            steps
            {
                script
                {
                    build("flask-app","latest","vaibhav237")
                }
            }
            
        }
        stage("Push")
        {
            steps
            {
                script
                {
                    PushImage("flask-app","latest","vaibhav237")
                }
            }
        }
        stage("Deploy")
        {
            steps
            {
                script
                {
                    deploy()
                }
            }
        }
        
    }
    
}
