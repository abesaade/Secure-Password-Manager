pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building'
                // Add your build commands here, e.g., compile Java
                // sh 'javac HelloWorld.java'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing'
                // Add your test commands here
                // sh 'java -cp . org.junit.runner.JUnitCore MyTests'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying'
                // Add your deployment commands here
                // sh './deploy.sh'
            }
        }
    }

    post {
        always {
            echo 'This will always run after the pipeline finishes.'
            // Clean up, archive logs, etc.
        }

        failure {
            echo 'Pipeline failed! You can notify your team or trigger alerts here.'
            // Send notifications, emails, or log failure status
        }
    }
}
