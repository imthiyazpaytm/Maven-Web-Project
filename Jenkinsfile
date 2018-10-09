#!groovy

node{
    stage('Checkout SCM'){
        checkout 'SCM'
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
