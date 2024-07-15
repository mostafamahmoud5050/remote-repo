pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'github-credentials-id', url: 'https://github.com/mostafamahmoud5050/remote-repo.git', branch: 'main'
            }
        }

        stage('Restart Docker Containers') {
            steps {
                script {
                    def webContainer = 'odoo-docker_web_1'
                    def dbContainer = 'odoo-docker_db_1'

                    sh "docker restart ${webContainer}"
                    sh "docker restart ${dbContainer}"
                }
            }
        }
    }
}
