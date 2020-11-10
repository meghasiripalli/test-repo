pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "Maven3.6.3"
    }

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/meghasiripalli/test-repo.git'

                // Run Maven on a Unix agent.
                //sh "mvn -Dmaven.test.failure.ignore=true clean package"

                // To run Maven on a Windows agent, use
                 bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }

           
        }
        stage('Deploy') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/meghasiripalli/test-repo.git'

                // To run Maven on a Windows agent, use
                 bat "mvn package deploy -DmuleDeploy"
            }

           
        }
    }
}
