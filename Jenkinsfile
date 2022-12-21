pipeline {
    agent any

    stages {

        stage('SonarQube analysis') {
            steps {
                withSonarQubeEnv('sonar') {
                    sh "./gradlew sonarqube"
                }
            }
        }
        stage("Quality gate") {
            steps {
                waitForQualityGate abortPipeline: true
            }
        }
    }
}
