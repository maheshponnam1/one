pipeline {
    agent any
tools{
maven 'maven 3.9.9'
}

    stages {
        stage('Checkout') {
        
            steps {
                echo 'Checking out code...'
                git 'https://github.com/maheshponnam1/one.git'
            }
        }

        stage('Build') {
            
            steps {
                echo 'Building the application...'
                sh 'mvn clean package'
            }
        }
        stage('SQREPORT'){
            steps{
                echo 'testing'
                sh 'mvn sonar:sonar'
            }
        }
        stage('deploy to nexus'){
            steps{
                sh 'mvn deploy'
            }
        }
    }
}
