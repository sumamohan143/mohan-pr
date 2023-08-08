pipeline {
    agent any

    stages {
        stage('Checkout PR Branch') {
            steps {
                script {
                    // Use the PR_REF environment variable to get the PR refspec
                    def prRef = env.CHANGE_REF
                    echo "PR Ref: ${prRef}"

                    checkout([$class: 'GitSCM', branches: [[name: prRef]], userRemoteConfigs: [[url: '']]])
                }
            }
        }

        stage('Build') {
            steps {
                // Your build steps here, using the content from the PR branch
                echo "Building using content from PR branch"
            }
        }
    }
}
