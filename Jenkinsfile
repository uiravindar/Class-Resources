pipeline {
    agent any

    stages {
        stage('Clone GitHub') {
            steps {
                echo 'Source code from our GitHub'
                git branch: 'main', url: 'https://github.com/uiravindar/Class-Resources.git'

            }
        }
		
		
		stage('Build') {
            steps {
                echo 'Building the code with Maven'
				sh 'mvn clean install'
            }
        }
		
		stage('Deploy') {
            steps {
                echo 'Deploy .war file to our Tomcat server'
                deploy adapters: [tomcat9(credentialsId: '4e3e5a09-39d0-420a-946c-6d4d70424b59', path: '', url: 'http://44.203.91.179:8081/')], contextPath: null, war: '**/*.war'

            }
        }
    }
}
