pipeline {
    agent {
        dockerContainer { image 'szymon321/stepik12.1' }
    }
    triggers {
    pollSCM('* * * * *')
}
    stages {
        stage("Checkout") {
            steps {
                git url: 'https://github.com/s24546/stepik-12.1.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'python3 calculator.py 3 3'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'python3 test_calculator.py'
            }
        }
    }
}

