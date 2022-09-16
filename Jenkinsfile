pipeline{
    agent any
    tools { 
        maven 'maven3'
    }
    stages
       {
            stage("clean")
            {
                steps{
                    sh "mvn clean"
                }
            }
            stage("Build")
            {
                steps{
                    sh "mvn compile"
                }
                
            }
            stage("TEST")
            {
                steps{
                    sh "mvn test"
                }
            }
            stage("package")
            {
                steps{
                    sh "mvn package"
                }
            }
    stage("Deploy")
            {
                steps{
                    sshagent(['Atishashauryaa']) {
                    sh "scp -o StrictHostKeyChecking=no   /home/atisha/.jenkins/workspace/final_project_Production/target/*.jar ubuntu@3.89.20.209:/home/ubuntu/"
                               
                 }
                }
            }    
    }
   
}
