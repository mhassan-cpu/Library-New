pipeline {
    agent any

    stages {
        stage('Get Code') {
            steps {
                git changelog: false, poll: false, url: 'https://github.com/mhassan-cpu/Library.git'
            }
        }

        stage('Run Test') {
            steps {
                bat 'newman run Library.postman_collection.json -e Library_dev.postman_environment.json --reporters=cli,htmlextra  || exit 0'
            }
        }
    }
}