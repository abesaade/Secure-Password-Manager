pipeline {
    agent any

    environment {
        MY_VERSION = '1.2.3'
    }

    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run tests?')
    }

    stages {
        stage('Build') {
            steps {
                echo "🔧 Building version ${env.MY_VERSION}"
                bat 'mvn install'
            }
        }

        stage('Test') {
            when {
                expression { return params.executeTests }
            }
            steps {
                echo '🧪 Running Tests'
                bat 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo '🚀 Deploying'
                // bat 'deploy.bat'
            }
        }
    }

    post {
        always {
            echo '🔁 This will always run after the pipeline.'
        }
        success {
            echo '✅ Build succeeded.'
        }
        failure {
            echo '❌ Build failed.'
        }
    }
}
