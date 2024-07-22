pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                echo 'Hello world!' 
            }
        }
        stage('SonarQube analysis') {
            steps {
                script {
                    scannerHome = tool 'sonarqubeScannerInstallation'// must match the name of an actual scanner installation directory on your Jenkins build agent
                }
                withSonarQubeEnv('sonarqubeInstallation') {// If you have configured more than one global server connection, you can specify its name as configured in Jenkins
                  sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}
