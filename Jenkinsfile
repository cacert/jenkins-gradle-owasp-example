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
                sh ' gradle check'
                dependencyCheckPublisher canComputeNew: true, canRunOnFailed: false, defaultEncoding: '', healthy: '', pattern: '', unHealthy: '', unstableTotalHigh: '0'
            }
        }
    }

}