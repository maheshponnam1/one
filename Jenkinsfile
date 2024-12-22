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
    }
}
