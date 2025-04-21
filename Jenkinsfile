pipeline {
    agent {label 'jenkins-worker1'}
    tools {
        jdk 'java17'
        maven 'maven3'
    }
    stages {
        stage("clean workspace") {
            steps {
                cleanWs()
            }
        }
        stage("checkout from SCM") {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/Vanphu2905/Devops-prj'
            }
        }
        stage("Build app") {
            steps {
                sh 'mvn clean package'
            }
        }
        stage("Test app") {
            steps {
                sh 'mvn test'
            }
        }
    }
}
