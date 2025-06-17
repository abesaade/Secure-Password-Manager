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
                bat 'mvn install'   // ✅ This line runs Maven if it's in your Windows PATH
            }
        }

        stage('Test') {
            when {
                expression { return params.executeTests == true }
            }
            steps {
                echo '🧪 Running Tests'
                bat 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo '🚀 Deploying'
                // bat 'deploy.bat' if you have a Windows deployment script
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
