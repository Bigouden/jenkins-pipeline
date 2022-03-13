pipeline {
    agent any
    stages {
        stage('Création Artefact') {
            steps {
                sh "echo `date` > date.txt"
                sh "tar cvfz date.tar.gz date.txt"
            }
        }
        stage('Upload Artefact') {
            steps {
                sh "ls -ralit"
            }
        }
    }
}
