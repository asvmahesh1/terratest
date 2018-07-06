pipeline {
    agent {
        node {
            label 'ecs-linux'
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
        stage('Ready') {
            steps {
                timeout(time:5, unit: 'MINUTES') {
                    input message: "Are we ready to proceed?"
                }
            }
        }
        stage('Provision-Final') {
            steps {
                echo 'Provisioning Deve....'
            }
        }        
        stage('Deploy-Final') {
            steps {
                echo 'Deploying....'
                echo 'doing more work'
            }
        }
        stage('Test-Final') {
            steps {
                echo 'Deploying....'
                echo 'doing more work'
                timeout(time:5, unit: 'MINUTES') {
                    input message: "Does http://localhost:8888/final/ look good?"
                }    
            }
        }
        stage('Setup Monitoring') {
            parallel {
                stage ('Update Deployment Statistics'){
                    steps {
                        echo 'Updating Run Dashboard'
                    }
                }
                stage ('Setup App Monitoring'){
                    steps {
                        echo 'Updating Run Dashboard'
                    }
                }
                stage ('Setup Log Analysis'){
                    steps {
                        echo 'Updating Run Dashboard'
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
