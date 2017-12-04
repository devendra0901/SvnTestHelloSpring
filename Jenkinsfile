pipeline {
    agent any

    tools {
        jdk 'java'
        maven 'maven3'
        docker 'org.jenkinsci.plugins.docker.commons.tools.DockerTool'
    }

    stages {
 
        stage('Build'){
            steps {
                sh 'printenv'
                sh 'mvn clean package'
 
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker-compose -f docker-compose.yml up -d --build --remove-orphans '
            }
        }
    }
}
