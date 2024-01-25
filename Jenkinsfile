pipeline {
    agent any
    
    stages {
        stage('Print Envs') {
            steps {
                sh 'printenv'
            }
        }

        stage('Git Version') {
            steps {
                script {
                    try {
                        tool 'Git' // Assume 'Git' is configured in Jenkins Global Tool Configuration
                        sh 'git version'
                    } catch (Exception ex) {
                        echo "Failed to install or get Git version: ${ex.message}"
                        currentBuild.result = 'FAILURE'
                        error(ex.message)
                    }
                }
            }
        }

        stage('Get Maven') {
            steps {
                script {
                    try {
                        tool 'Maven' // Assume 'Maven' is configured in Jenkins Global Tool Configuration
                        sh 'mvn --version'
                    } catch (Exception ex) {
                        echo "Failed to install or get Maven version: ${ex.message}"
                        currentBuild.result = 'FAILURE'
                        error(ex.message)
                    }
                }
            }
        }

        stage('Get Docker') {
            steps {
                script {
                    try {
                        tool 'Docker' // Assume 'Docker' is configured in Jenkins Global Tool Configuration
                        sh 'docker --version'
                    } catch (Exception ex) {
                        echo "Failed to install or get Docker version: ${ex.message}"
                        currentBuild.result = 'FAILURE'
                        error(ex.message)
                    }
                }
            }
        }

        stage('Get httpd') {
            steps {
                script {
                    try {
                        tool 'Httpd' // Assume 'Httpd' is configured in Jenkins Global Tool Configuration
                        sh 'httpd -version'
                    } catch (Exception ex) {
                        echo "Failed to install or get Httpd version: ${ex.message}"
                        currentBuild.result = 'FAILURE'
                        error(ex.message)
                    }
                }
            }
        }
    }
}
