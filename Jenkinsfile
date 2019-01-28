pipeline {
    agent { label 'vm_name' } // "vm_name" is the lable of instance, where the test will take place.

    stages {
        stage ('Configure test rails env') {
            steps {
                dir('rails_app') { // "dir" block changes the jenkins default workdir to your app dir.
                    sh 'pwd'
                    sh 'bundle install' // Runs bundle install to update gems.
                }
            }
        }
        stage ('Run rspec tests') {
            steps {
                dir('rails_app') { // "dir" block changes the jenkins default workdir to your app dir.
                    sh 'bundle exec rspec -f d spec' // Runs RSpec tests in the spec directory.
                }
            }
        }
    }
}
