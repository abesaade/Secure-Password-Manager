pipeline {
    agent any

    stages {
        stage('Print PATH') {
            steps {
                bat 'echo %PATH%'
            }
        }
        stage('Maven Check') {
            steps {
                bat 'mvn -version'
            }
        }
    }
}
