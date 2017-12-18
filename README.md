# terratest
  configure { project ->
        def bindings = project / 'buildWrappers' / 'org.jenkinsci.plugins.credentialsbinding.impl.SecretBuildWrapper' / 'bindings'
        bindings << 'com.cloudbees.jenkins.plugins.awscredentials.AmazonWebServicesCredentialsBinding' {
            accessKeyVariable("AWS_ACCESS_KEY_ID")
            secretKeyVariable("AWS_SECRET_ACCESS_KEY")
            credentialsId("credentials-id")
        }
    }
