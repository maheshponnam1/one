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
        stage('deploy to tomcat'){
            steps{
                sshagent(['3b3f05e1-7e79-4a72-8bac-3f1bddf03262']) {
                    sh "scp -o StrictHostKeyChecking=no target/myweb-8.5.5.war ec2-user@34.228.6.20:/opt/apache-tomcat-9.0.98/webapps"
    // some block
}
            }
        }
    }
}
