pipeline{
    agent any

    stages{
        stage('zip the file'){
            steps{
                sh 'zip ansible-${BUILD_ID}.zip * --exclude Jenkinnksfile'
            }
        }
        stage('upload artifacts to jfrod'){
            steps{
                sh 'curl -uadmin:AP8gcgmmset5jeYChTJYDN6XmDd -T \
                 ansible-${BUILD_ID}.zip \
                "http://100.27.14.207:8081/artifactory/ansible/ansible-${BUILD_ID}.zip"'
            }
        }
    }
}