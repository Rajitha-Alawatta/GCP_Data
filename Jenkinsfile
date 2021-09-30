pipeline {
    agent any
        environment {
            GIT_REPO = 'https://github.com/Rajitha-Alawatta/GCP_Data.git'
            REPO_FOLDER = 'GCP_Data'
            TEST_PROJECT_ID = "test-environment-262811"
            PROD_PROJECT_ID = "production-environment-327608"
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
        stage('Set GCP Project - Test') {
            steps {
                sh "gcloud config set project ${TEST_PROJECT_ID}"
            }
        }
        stage('Get VMs in Test Project') {
            steps {
                sh "gcloud compute instances list"
            }
        }
        stage('Set GCP Project - Production') {
            steps {
                sh "gcloud config set project ${PROD_PROJECT_ID}"
            }
        }
        stage('Get VMs in Production Project') {
            steps {
                sh "gcloud compute instances list"
            }
        }
    }
}