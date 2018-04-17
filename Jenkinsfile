pipeline{
    agent any

        tools {
            gradle 'gradle'
        }

    stages{
        stage('deneme'){

            steps{
                sh 'gradle clean test'
            }
        }
        stage ('OWASP Dependency Check'){
            steps {
                dependencyCheckAnalyzer includeCsvReports: false, includeHtmlReports: false, includeJsonReports: false, includeVulnReports: false, isAutoupdateDisabled: false,  skipOnScmChange: false, skipOnUpstreamChange: false
                dependencyCheckPublisher canComputeNew: false, defaultEncoding: '', healthy: '', pattern: '', unHealthy: ''            }
        }
    }
}