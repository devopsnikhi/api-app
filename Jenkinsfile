pipeline {
    agent any

    tools {
        maven "maven"
    }

    stages {
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/devopsnikhi/api-app.git'
                sh "mvn -Dmaven.test.failure.ignore=true clean package"
            }
            post {  
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
        stage('deploy') {
            steps {
                echo "hello iam deploying"
            }  
        }
        stage('test') {
            steps {
                echo "hello iam test"
            }  
        }
    }
}
