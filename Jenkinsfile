pipeline {
    agent any

    stages {
        stage('SCM Stage') {
            steps {
                echo 'pradeep'
                git 'https://github.com/wakaleo/game-of-life.git'
            }
        }
        
        stage('Artifact build stage') {
            steps {
                echo 'building with maven'
                sh 'mvn clean install'
            }
        }
        
        stage('Deploy on tomcat') {
            steps {
                echo 'deploying to pradeep lab tomcat'
                deploy adapters: [tomcat9(credentialsId: '20976672-1819-4e68-99e3-e74315839586', path: '', url: 'http://3.21.185.67:8080/')], contextPath: null, war: '**/*.war'
            }
        }
        
    }
}
