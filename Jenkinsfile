// This is a Declarative Pipeline
pipeline {
    agent any // This tells Jenkins to run the pipeline on any available agent (including the controller itself if no agents are defined)

    stages {
        stage('Prepare') {
            steps {
                echo 'Preparing the build environment...'
                // You could add setup steps here, e.g., installing dependencies
            }
        }
        stage('Build') {
            steps {
                echo 'Starting the build process...'
                // Execute your build script from the previous lesson
                // Make sure your build_script.sh (or .bat) is executable and in your repo
                sh './build_script.sh' // For Linux/macOS
                // bat 'build_script.bat' // Uncomment and use for Windows
            }
        }
        stage('Report') {
            steps {
                echo 'Generating build report...'
                // List files in the workspace to confirm they are there
                sh 'ls -F' // For Linux/macOS
                // bat 'dir' // Uncomment and use for Windows
                echo 'Build process completed successfully!'
            }
        }
    }
    post {
        always {
            echo 'This will always run, regardless of success or failure.'
        }
        success {
            echo 'Pipeline finished with SUCCESS!'
        }
        failure {
            echo 'Pipeline finished with FAILURE!'
        }
    }
}