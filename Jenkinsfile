pipeline {
    agent any
    stages {
        stage('Cleaning the cluster') {
            steps {
                sh 'kubectl delete deployments myapp -n nginx-app-namespace'
                sh 'kubectl delete deployments mysqldbi -n nginx-app-namespace'
                sh 'kubectl delete svc mysqldb-svc -n nginx-app-namespace'
                sh 'kubectl delete svc myapp-svc -n nginx-app-namespace'
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