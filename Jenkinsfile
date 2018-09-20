pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '/usr/local/maven/bin/mvn  package'
            }
        }
        stage('Deploy') {
            steps {
                sh 'sudo ssh  root@yilei.node2.com "sudo sh /usr/local/deploy_tomcat.sh"'
            }
        }
    }
}
