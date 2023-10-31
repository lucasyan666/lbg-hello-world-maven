pipeline {
    agent any
    
    tools {
        //Install the maven version configured as "M3" and add it to the path
        //testing again
        maven "M3"
    }
    
    stages {
        stage('Checkout') {
            steps {
                //get some code from a github repository
                
                git branch: 'main', url: 'https://github.com/lucasyan666/lbg-hello-world-maven.git'
            }
        }
        stage('Compile') {
            steps {
                //run maven on a unix agent
                sh "mvn clean compile"
            }
        }
        stage('Test') {
            steps {
                sh "mvn test"
            }
        }
        stage('Package') {
            steps {
                sh "mvn -Dmaven.test.skip -Dmaven.compile.skip package"
            }
        }
    }
}