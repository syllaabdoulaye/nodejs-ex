pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3000:3000' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        } 
        stage('SonarQube Analysis') {
           sh "/var/jenkins_home/sonar-scanner/sonar-scanner-3.3.0.1492-linux/bin/sonar-scanner -Dsonar.host.url=http://localhst:9000 -Dsonar.projectName=nodejs-ex -Dsonar.projectVersion=1.0 -Dsonar.projectKey=nodejs-ex:app -Dsonar.sources=. 
        }
    } 
 
} 
