pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                bat 'rmdir /Q /s GitTojenkins'
                git branch: 'main', credentialsId: 'b9817ad1-4ec4-41b9-a1e8-b074aaceca2d', url: 'https://github.com/QANaveen/gittojen.git'
                bat 'mvn clean -f GitTojenkins'
            }
        }
    }
    post { 
        failure { 
                git branch: 'main', credentialsId: 'b9817ad1-4ec4-41b9-a1e8-b074aaceca2d', url: 'https://github.com/QANaveen/gittojen.git'
                bat 'mvn clean -f GitTojenkins'
        }
    }
}
               
