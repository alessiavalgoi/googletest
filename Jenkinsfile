pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Cloning GitHub repository ...'
                git branch: 'main', url: 'https://github.com/alessiavalgoi/googletest.git'
                sh 'ls'
                dir('googletest/samples') {
                sh 'g++ -o sample1_test sample1_unittest.cc sample1.cc -lgtest -lgtest_main'
                sh 'g++ -o sample2_test sample2_unittest.cc sample2.cc -lgtest -lgtest_main'
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                 dir('googletest/samples'){
                sh './sample1_test'
                sh './sample2_test'
                 }
            }
        }
    }
}
