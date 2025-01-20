pipeline {
    agent any

    stages {
        stage('clear') {
            steps {
                sh '''rm -r -f "/root/lesson6"
                rm -r -f "/root/test"'''
            }
        stage('create_text_file') {
            steps {
                sh '''mkdir "/root/lesson6"
                cd "/root/lesson6"
                echo "tal" > tal.txt'''
            }
        }
        stage('echo_text_file') {
            steps {
                sh '''cd "/root/lesson6"
                cat tal.txt'''
            }
        }
        stage('echo_free_disk') {
            steps {
                sh 'df -h --output=avail / | tail -n +2'
            }
        }
        stage('move_test_file') {
            steps {
                sh '''mkdir "/root/test"
                mv /root/lesson6/tal.txt /root/test/'''
            }
        }
    }
}
