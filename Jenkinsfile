pipeline {
    agent: any

    stages {
        stage('Updating Index') {
            sudo apt update
        }

        stage('Installink Apache2') {
            sudo apt install apache2 -y
        }
    }
}