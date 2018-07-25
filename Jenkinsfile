pipeline {
    agent {
        node {
            label 'fargate'
        }
    }
    triggers {
        pollSCM('H/5 * * * *')
    }
    stages {
        stage('Plan Update') {
            steps {
                echo 'Updating Jira Info...'
            }
        }
        stage('Source Control Checks'){
            steps {
                input message: "Has source code gone through the required checks?"
            }
        }
         stage('Build') {
             steps {
                 echo 'Building artifacts'
             }

        }
        stage('Unit Testing'){
            steps {
                echo 'Testing...'
                echo 'Adding more tests'
            }
        }
        stage('Code Quality Checks') {
            steps {
                echo 'Deploying....'
                echo 'doing more work'
            }
        }
        
        stage('Store Artifacts') {
            steps {
                echo 'Deploying....'
                echo 'doing more work'
            }
        }
        stage('Provision-Phase1') {
            steps {
                echo 'Provisioning Environment....'
            }
        }        
        stage('Deploy-Phase1') {
            steps {
                echo 'Deploying....'
                echo 'doing more work'
            }
        }        
        stage('Test-Phase1') {
            parallel {
                stage ('Solenium') {
                    steps {
                        echo 'Executing Solenium'
                        echo 'doing more work'

                    }
                }
                stage ('LoadRunner'){
                    steps {
                        echo "Running tests...."
                    }
                }
            }

        }
        stage('Cleanup') {
            steps {
                echo 'Finished Cleanup'
            }
        }
    }
}
