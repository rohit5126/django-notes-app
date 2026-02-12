@Library("shared") _
pipeline {
    agent { label "slave" }

    stages {
        stage("hello ttt") {
            steps {
                script {
                    hello()
                }
            }
        }
        stage('Copy code from github') {
            steps {
                script{
                    clone("https://github.com/rohit5126/django-notes-app.git","main")
                }
            }
        }
    stage('docker installation') {
            steps {
                script{
                    installdocker()
                }
                
            }
        }
    stage('build and deploy') {
            steps {
                script {
                    build()
                }
            }
        }
    stage('push to docker hub') {
            steps {
                script {
                    pushDocker("rohit5126/django_app:latest")
                    
                }
                
            }
        }    
    }
}
