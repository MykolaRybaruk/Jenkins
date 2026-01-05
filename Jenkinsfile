pipeline {
    agent any

    stages {
        stage('Updating index') {
            steps {
                sh 'sudo apt update'
            }
        }

        stage('Installing Apache2') {
            steps {
                sh 'sudo apt install apache2 -y'
            }
        }

        stage ('Launching Apache2 and adding to autostart') {
            steps {
                sh 'sudo systemctl start apache2'
                sh 'sudo systemctl enable apache2'
            }
        }

        stage ('Searching 4xx and 5xx errors') {
            steps {
                sudo grep -E (4|5)[0-9]{2} /var/log/apache2/access.log
            }
        }
    }
}