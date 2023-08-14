pipeline {
    agent any
    
    parameters {
        string(name: 'PR_NUMBER', defaultValue: '', description: 'Enter the PR number')
    }
    
    stages {
        stage('Checkout PR Branch') {
            steps {
                script {
                    def prNumber = params.PR_NUMBER
                    echo "PR Number: ${prNumber}"
                    
                    checkout([$class: 'GitSCM',
                        branches: [[name: "refs/pull/${prNumber}/merge"]],
                        doGenerateSubmoduleConfigurations: false,
                        extensions: [[$class: 'CleanBeforeCheckout']],
                        userRemoteConfigs: [[url: 'https://github.com/sumamohan143/mohan-pr.git']]
                    ])
                }
            }
        }
        
        stage('Build') {
            steps {
                // Your build steps here, using the content from the PR branch
                echo "Your build steps here, using the content from the PR branch"
            }
        }
    }
}
