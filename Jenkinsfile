pipeline {
    agent any
    
    tools {
        maven 'M3100'
    }

    stages {
        stage('Echo version') {
            steps {
                sh 'echo Print Maver Version'
                sh 'mvn -version'
            }
        }
        
        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests=true'
            }
        }
        
        stage('Test') {
            steps {
                script {
                    for (int i = 0; i < 60; i++) {
                        echo '${i + 1}'
                        sleep 1
                    }
                         
                    sh 'mvn test'
                }
            }
        }
    }
}
