pipeline {
    agent any
    tools {
        maven 'maven-3.8.5'   
     }

    stages {
        stage("Git Checkout") {
            steps {
                git branch: 'main', credentialsId: 'Git_credential',
                url: 'https://github.com/Raghav8125/Ansible_podman_pipeline.git'
            }
        }
       stage("Maven Build"){
            steps{
                sh "mvn clean package"
            }
        }
        stage("Execute ansible"){
            steps{
              ansiblePlaybook credentialsId: 'dev-server', disableHostKeyChecking: true, installation: 'ansible', inventory: 'dev.inv', playbook: 'podman.yml'
            }
        }
    }//stages
}//pipeline
