pipeline {
    agent any
    stages {
        stage('Cleaning the cluster') {
            steps {
                echo 'Hello'
                //sh 'kubectl delete pvc mysql-pvc -n myapp-namespace'
                //sh 'kubectl delete deployments myapp -n myapp-namespace'
                //sh 'kubectl delete deployments mysqldbi -n myapp-namespace'
                //sh 'kubectl delete svc mysqldb-svc -n myapp-namespace'
                //sh 'kubectl delete svc myapp-svc -n myapp-namespace'
                //sh 'kubectl delete namespace myapp-namespace'
                sh 'kubectl create namespace myapp-namespace'
                }
            }

        stage('Deploying the MySQL container') {
            steps {
                sh 'kubectl apply -f mysql-deployment.yaml -n myapp-namespace'
                }
            }

        stage('Deploying the Web Application container') {
            steps {
                sh 'kubectl apply -f app-deployment.yaml -n myapp-namespace'
                }
            }

        }
    }