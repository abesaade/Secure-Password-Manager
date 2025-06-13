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
}
