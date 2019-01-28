pipeline {
    agent { label 'vm_name' } // "vm_name" is the lable of instance, where the test will take place.

    stages {
        stage ('Configure test rails env') {
            steps {
                dir('app_dir') { // "dir" block changes the jenkins default workdir to your app directory.
                    sh 'pwd'
                    sh 'bundle install' // Runs bundle install to update gems.
                }
            }
        }
        stage ('Run rspec tests') {
            steps {
                dir('app_dir') {
                    sh 'bundle exec rspec -f d spec' // Runs RSpec tests in the spec directory.
                }
            }
        }
    }
}
