pipeline {
    agent any

    stages {
        stage('Check Maven') {
            steps {
                bat 'mvn -version'  // ✅ Will now work if Maven is in system PATH
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean install'  // ✅ Build your Maven project
            }
        }
    }

    post {
        always {
            echo '✅ Pipeline completed.'
        }
        success {
            echo '🎉 Build succeeded.'
        }
        failure {
            echo '❌ Build failed.'
        }
    }
}
