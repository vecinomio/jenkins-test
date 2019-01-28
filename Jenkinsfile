pipeline {
    agent { label 'name1' } // "name1" is the label of instance, where the test will take place.

    stages {
        stage ('Environment preporation') {
            steps {
                dir('app_dir') { // "dir" block changes the jenkins default workdir to your app directory.
                    sh 'pwd' // Check changed directory.
                    sh 'bash preporation.sh' // Executes the command for stage "Environment preporation".
                }
            }
        }
        stage ('Tests') {
            steps {
                dir('app_dir') {
                    sh 'bash test.sh' // Executes the command for stage "Tests".
                }
            }
        }
    }
}
