pipeline {
    agent any

    tools {
        maven 'Maven 3.8.6'  
    }

    environment {
        MY_VERSION = '1.2.3'
    }

    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run tests?')
    }

    stages {
        stage('Build') {
            steps {
                echo "Building version ${env.MY_VERSION}"
                bat 'mvn install'
            }
        }

        stage('Test') {
            when {
                expression { return params.executeTests == true }
            }
            steps {
                echo 'Testing only when condition is met'
                bat 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying'
                // bat 'deploy.bat'
            }
        }
    }

    post {
        always {
            echo 'This will always run after the build.'
        }
        success {
            echo 'This runs if build succeeds.'
        }
        failure {
            echo 'This runs if build fails.'
        }
    }
}
