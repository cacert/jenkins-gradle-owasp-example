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
    }

}