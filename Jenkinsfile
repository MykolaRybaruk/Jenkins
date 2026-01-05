pipeline {
    agent: any

    stages {
        stage('Updating Index') {
            sudo apt update
        }

        stage('Installink Apache2') {
            sudo apt install apache2 -y
        }

        stage('Launching Jenkins and adding to AutoStart') {
            sudo systemctl start apache2
            sudo systemctl enable apache2
        }

        stage('Searching for 4xx and 5xx errors') {
            sudo grep -E  (4|5)[0-9]{2}  /var/log/apache2/access.log
        }
    }
}