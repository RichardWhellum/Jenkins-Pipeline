pipeline {
    agent any

    environment {
        DIRECTORY_PATH = "/path/to/code"
        TESTING_ENVIRONMENT = "Test environment"
        PRODUCTION_ENVIRONMENT = "Richard Whellum"
    }
    stages {
        stage("Build") {
            steps {
                echo "Fetch the source code from the directory path: $DIRECTORY_PATH"
                echo "Compile the code and generate any necessary artifacts"
            }
        }
        stage("Test") {
            steps {
                echo "Unit tests"
                echo "Integration tests"
            }
        }
        stage("Code Quality Check") {
            steps
            {
                echo "Check the quality of the code"
            }
        }
        stage("Deploy") {
            steps {
                echo "Deploy the application to a testing environment: $TESTING_ENVIRONMENT"
            }
        }
        stage("Approval") {
            steps {
                echo "Waiting for manual approval..."
                sleep 10
            }
        }
        stage("Deploy to Production") {
            steps {
                echo "Deploying the code to production environment: $PRODUCTION_ENVIRONMENT"
            }
        }
    }
}