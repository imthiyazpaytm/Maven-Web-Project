#!groovy

node{
    stage('Checkout SCM'){
        git changelog: false, credentialsId: 'c626f746-2735-44c4-a216-b8638348f2e4', poll: false, url: 'https://github.com/imthiyazpaytm/Maven-Web-Project.git'
    }
    stage('Building and deploying artifact'){
        bat 'mvn clean deploy'
    }
    stage('SonarQube'){
        bat 'mvn sonar:sonar'
    }
    stage('Tomcat Deployment'){
        bat 'copy %WORKSPACE%\\target\\*.war "D:\\DevOps Stuff\\apache-tomcat-9.0.10\\webapps"'
    }
}
