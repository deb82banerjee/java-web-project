pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                sh "mvn clean package"
            }
        }
        stage("Deploy"){
            steps{
                deploy adapters: [tomcat7(credentialsId: 'd00d72b7-df0c-49e4-a640-e06077cf35e1', path: '', 
                url: 'http://ec2-3-129-89-10.us-east-2.compute.amazonaws.com:8080/')], 
                contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
