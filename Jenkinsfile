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
        stage('package'){

                    steps{
                        sh 'gradle build'
                    }
                }
        stage ('OWASP Dependency Check'){
            steps {

            sh './gradlew dependencyCheckAnalyze '
                //dependencyCheckAnalyzer datadir: '', hintsFile: '', includeCsvReports: false, includeHtmlReports: false, includeJsonReports: false, isAutoupdateDisabled: false, outdir: '', scanpath: '${WORKSPACE}', skipOnScmChange: false, skipOnUpstreamChange: false, suppressionFile: '', zipExtensions: '',includeVulnReports: false

                //dependencyCheckPublisher canComputeNew: false, defaultEncoding: '', healthy: '85', pattern: '**/dependency-check-report.xml', shouldDetectModules: true, unHealthy: ''
                dependencyCheckPublisher canComputeNew: false
           }
        }
    }
}