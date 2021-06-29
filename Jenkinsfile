pipeline {
    agent any 
    stages {
        stage('Git-SCM') { 
            steps {
                git credentialsId: 'Freestyleproject', url: 'https://github.com/krishnavagu/paypalbank.git'
            }
        }
        stage('Build') { 
            steps {
                echo "This is my Test Stage" 
                sh label: '', script: 'mvn clean package'
            }
        }
        stage('Deploy') { 
            steps {
                echo "This is my Deploy stage"
                deploy adapters: [tomcat9(credentialsId: 'Deployment', path: '', url: 'http://54.88.188.19:8089/')], contextPath: null, war: '**/*.war' 
            }
        }
    }
}
