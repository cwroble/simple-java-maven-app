pipeline {
agent {
        node {
          label 'maven'
        }
      }
    
    stages {
        stage('Build') {
            steps {
                container('maven') {
                sh 'mvn -B -DskipTests clean package'
                }
            }
        }
        stage('Test') {
            steps {
                container('maven') {
                sh 'mvn test'
                }
            }
            
        }
        stage('Deliver') {
            steps {
                container('maven') {
                sh './jenkins/scripts/deliver.sh'
                }
            }
        }
    }
}
