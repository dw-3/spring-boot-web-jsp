pipeline {
    agent { node { label 'slave' } }
      stages {
        stage('build') {
            steps {
                sh 'mvn package'
            }
        }
    stages {
        stage('docker') {
            agent {
                docker { image 'tomcat' }
                agrs '-v /usr/local/tomcat/webapps:/usr/local/tomcat/webapps' 
            }
            steps {
                sh 'cp /var/lib/jenkins/workspace/'
            }
        }
        stage('Front-end') {
            agent {
                docker { image 'node:7-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
