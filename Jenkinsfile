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
                echo "Building version ${env.MY_VERSION}"
                // Add your build commands here
                // sh 'javac HelloWorld.java'
            }
        }

        stage('Test') {
            when {
                expression { return params.executeTests == true }
            }
            steps {
                echo 'Testing only when condition is met'
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
