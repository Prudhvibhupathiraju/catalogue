pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        packageversion = ''
    }
    stages {
        stage('get the version'){
            steps{
                script {
                    def packagefile = readJSON file: 'package.json'
                    packageversion = packagefile.version
                    echo "application verion is ${packagefile.version}"
                            }
            }
        }
        stage('Install dependencies'){
            steps{
                script {
                    sh """
                    npm install
                    """
                            }
            }
        }
    }
}   
