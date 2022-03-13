pipeline {
    agent any
    environment {
        NEXUS_VERSION = "nexus3"
        NEXUS_PROTOCOL = "http"
        NEXUS_URL = "nexus.internal:8081"
        NEXUS_REPOSITORY = "test"
        NEXUS_CREDENTIAL_ID = "nexus-credentials"
    }
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
                nexusArtifactUploader(
                    nexusVersion: NEXUS_VERSION,
                    protocol: NEXUS_PROTOCOL,
                    nexusUrl: NEXUS_URL,
                    version: 'DATE-SNAPSHOT,
                    repository: NEXUS_REPOSITORY,
                    credentialsId: NEXUS_CREDENTIAL_ID,
                    artifacts: [
                        [artifactId: pom.artifactId,
                         classifier: '',
                         file: 'date.tar.gz',
                         type: 'tar.gz'],
                    ]
                )
            }
        }
    }
}
