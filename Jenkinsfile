pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/LorettaEpuechi/MyProject.git'
            }
        }
        
   stage('Build with Maven') {
            steps {
                sh 'cd SampleWebApp && mvn package'
            }
        }
        
   stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'mytomcat', path: '', url: 'http://18.206.160.18:8080/')], contextPath: 'mypath', war: '**/*.war'
            }
        }
    }
}
