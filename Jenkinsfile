pipeline{
    agent any

    tools{
        maven 'maven3.9'
    }
    stages{
        stage("Checkout Code"){
            steps{
                git branch: 'master', url: 'https://github.com/hemant-avd/java-web-app.git'
            }
        }
        stage("Build Code"){
            steps{
                sh 'mvn clean package'
            }
        }
        stage("Deployment"){
            steps{
                deploy adapters: [tomcat9(url: 'http://54.242.147.159:8080/', credentialsId:'tomee')] , war:'target/*.war'
            }
        }
    }
}
