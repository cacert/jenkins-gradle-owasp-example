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
                dependencyCheckAnalyzer datadir: '', hintsFile: '', includeCsvReports: false, includeHtmlReports: false, includeJsonReports: false, isAutoupdateDisabled: false, outdir: '', scanpath: '**/*.jar,**/pom.xml', skipOnScmChange: false, skipOnUpstreamChange: false, suppressionFile: '', zipExtensions: ''

                dependencyCheckPublisher canComputeNew: false, defaultEncoding: '', healthy: '85', pattern: '**/dependency-check-report.xml', shouldDetectModules: true, unHealthy: ''
            }
        }
    }
}