pipeline{

    agent any

    stages {

        stage ('Compile Stage') {

            steps {

                withMaven {
                    sh 'mvn clean verify'

                }

            }
        }
    stage ('Test Stage') {

            steps {

                withMaven {
                    sh 'mvn test'

                }

            }
        }


        stage ('Cucumber Reports') {

            steps {
                cucumber buildStatus: "UNSTABLE",
                    fileIncludePattern: "**/cucumber.json",
                    jsonReportDirectory: 'target'

            }

        }

    }

}