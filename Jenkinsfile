pipeline {
    agent any
        environment {
            GIT_REPO = 'https://github.com/Rajitha-Alawatta/GCP_Data.git'
            REPO_FOLDER = 'GCP_Data'
            OS = 'webserver-image'
            IMAGE_NAME = "test-image"
            PROJECT = "test-environment-262811"
            SOURCE_VM = "base-vm"
            SOURCE_DISK_ZONE = "us-central1-a"
            STORAGE_LOCATION = "us"
            PRIVATE_KEY = '/home/jenkins/.ssh/id_rsa'

        }

    stages {
        stage('Terraform Started') {
            steps {
                sh 'echo "Script started..!" '
            }
        }
        stage('Clone Repo') {
            steps {
                sh "rm -rf ${REPO_FOLDER}"
                sh "git clone ${GIT_REPO}"
            }
        }
        stage('Create Image') {
            steps {
                sh "gcloud compute instances list"
            }
        }
    }
}