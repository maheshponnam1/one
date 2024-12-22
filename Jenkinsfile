pipeline {
    agent none
tools{
maven 'maven 3.9.9'
}

    stages {
        stage('Checkout') {
            agent { label 'slaves' }
            steps {
                echo 'Checking out code...'
                git 'https://github.com/maheshponnam1/one.git'
            }
        }

        stage('Build') {
            agent { label 'slaves' }
            steps {
                echo 'Building the application...'
                sh 'mvn clean package'
            }
        }
    }
}
