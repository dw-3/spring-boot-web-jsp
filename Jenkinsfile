pipeline {
    agent any
    //agent { node { label 'slave' } }
      stages {
        stage('build') {
            steps {
                sh '/usr/local/maven/bin/mvn package'
            }
        }
        stage('docker') {
            agent {
                docker { 
                image 'tomcat' 
                args '-v /usr/local/tomcat/webapps:/usr/local/tomcat/webapps'
                       }
            }
            steps {
                sh 'cp /var/lib/jenkins/workspace/test-pipeline/spring-boot-web-jsp-${branch}.war /usr/local/tomcat/webapps/ROOT.war'
                  }
            }
      }
}
 
