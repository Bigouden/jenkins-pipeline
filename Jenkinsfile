pipeline {
    agent any
    stages {
        stage('Initialisation') {
            steps {
                git url: 'https://github.com/Bigouden/jenkins-pipeline.git', branch: 'master'
            }
        }
        stage('Test') {
            steps {
                echo "toto"
            }
        }
    }
}
