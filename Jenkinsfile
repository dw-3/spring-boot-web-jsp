pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '/usr/local/maven/bin/mvn -B –Dmaven.test.failure.ignore=true clean package'
            }
        }
        stage('Deploy') {
            steps {
                sh 'ssh  yilei.node2.com "sh /usr/local/deploy_tomcat.sh"'
            }
        }
    }
}
