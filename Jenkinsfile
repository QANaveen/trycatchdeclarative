pipeline {
    agent any
    tools {
      maven 'MAVEN_HOME'
     }
    stages {
        stage('maven version')
        {
           steps
            {
                bat 'mvn -v'
            }
        }   
        stage('clone') {
            steps {
                script
                {
                try
                {
               
                git branch: 'main', credentialsId: 'b9817ad1-4ec4-41b9-a1e8-b074aaceca2d', url: 'https://github.com/QANaveen/gittojen.git'
                bat 'mvn clean -f GitTojenkins'
                }
                catch(Exception e)
                {
                echo 'helloworld'  
                } 
                }    
            }
        }
        stage('Test')
        {
           steps
            {
                bat 'mvn test -f GitTojenkins'

            }
        }
        stage('Build')
        {
           steps
            {
                bat 'mvn package -f GitTojenkins'

            }
        }
    }
} 
