pipeline {
    agent any
    
    tools{
        jdk 'jdk11'
        maven 'maven'
    }

    stages {
        stage('Git checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/nikhilphule88/Petclinic.git'
            }
        }
        stage('Compile') {
            steps {
                sh "mvn clean compile"
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTest=True'
            }
        }
        stage('Deploy') {
            steps {
                sh 'sudo cp target/petclinic.war /opt/apache-tomcat-9.0.65/webapps'
            }
        }
    }
}
