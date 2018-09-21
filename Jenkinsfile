pipeline {
    agent { node { label 'slave' } }
      stages {
        stage('build') {
            steps {
                sh 'mvn package'
            }
        }
        stage('docker') {
            agent {
                docker { image 'tomcat' }
                agrs '-v /usr/local/tomcat/webapps:/usr/local/tomcat/webapps' 
            }
            steps {
                sh 'cp /var/lib/jenkins/workspace/workspace/test-pipeline/spring-boot-web-jsp-${branch}.war /usr/local/tomcat/webapps/ROOT.war'
                  }
            }
            }
        }
