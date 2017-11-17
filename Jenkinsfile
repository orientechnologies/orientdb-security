#!groovy
node("master") {
    def mvnHome = tool 'mvn'
    def mvnJdk7Image = "orientdb/mvn-gradle-zulu-jdk-7"

    stage('Source checkout') {

        checkout scm
    }

    stage('Tests on Java7') {
        docker.image("${mvnJdk7Image}").inside("--memory=4g ${env.VOLUMES}") {
            try {

                sh "${mvnHome}/bin/mvn  --batch-mode -V -U  clean install  -Dsurefire.useFile=false"

            } catch (e) {
                currentBuild.result = 'FAILURE'

                slackSend(channel: '#jenkins-failures', color: 'bad', message: "FAILED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})\n${e}")
            } finally {
                junit allowEmptyResults: true, testResults: '**/target/surefire-reports/TEST-*.xml'

            }
        }
    }

}



