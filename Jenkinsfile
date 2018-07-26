#!/usr/bin/env groovy
import hudson.model.*
import hudson.EnvVars
import jenkins.tasks.SimpleBuildWrapper
import groovy.json.JsonSlurperClassic
import groovy.json.JsonBuilder
import groovy.json.JsonOutput
import java.net.URL


pipeline {
    agent any
     stages {
        stage ('Main Stage') {
            steps {
                script {
                    if (env.BRANCH_NAME == "dbaas") {
					   
                        stage ('Stage 1') {
						     script {
                            sh 'echo Stage 1'
							}
                        }
                    }
                    if (env.BRANCH_NAME == "master") {
                        stage ('Stage 2') {
                            sh 'echo Stage 2'
                        }
                    }
                }
            }
        }
    }
}
