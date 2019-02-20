pipeline {
    agent {
        node {
            label 'master'
        }
    }

    stages {

        stage('terraform started') {
            steps {
                sh 'echo "Started...!" '
            }
        }
        stage('git clone') {
            steps {
                sh 'rm -r *;sudo git clone https://github.com/nguyenvandan/jenkins.git'
            }
        }
        stage('tfsvars create'){
            steps {
                sh 'cp /home/ubuntu/vars.tf ./jenkins/'
            }
        }
        stage('terraform init') {
            steps {
                sh '/home/ubuntu/terraform init ./jenkins'
            }
        }
        stage('terraform plan') {
            steps {
                sh 'ls ./jenkins; /home/ubuntu/terraform plan ./jenkins'
            }
        }
        stage('terraform ended') {
            steps {
                sh 'echo "Ended....!!"'
            }
        }

        
    }
}
