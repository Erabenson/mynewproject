pipeline {
    agent any

    stages {
        stage('Git Integration') {
            steps {
                git 'https://github.com/Erabenson/mynewproject.git'
            }
        }
        stage('Build') {
            steps {
                sh 'cd MyWebApp/ && mvn clean package'
            }
        }
        stage('Test') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://13.56.231.214:8080/')], contextPath: 'webapp', war: '**/*.war'
            }
        }
    }
}
