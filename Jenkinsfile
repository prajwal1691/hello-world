pipeline {
    agent {label 'slave01'}

    stages {
        stage('BUILD') {
            steps {
                git branch: 'main', url: 'https://github.com/prajwal1691/hello-world'
                sh '''cd /home/ec2-user/jenkins/workspace/agentpipeline
                mvn clean install'''
            }
        }
        stage('DEPLOY') {
            steps {
               sh '''cd /home/ec2-user/jenkins/workspace/agentpipeline/target
                sudo cp *.war /opt/tomcat9/webapps'''
            }
        }
    }
}