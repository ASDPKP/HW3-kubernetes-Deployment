pipeline {
    stage('Cleaning the cluster') {
        steps {
            sh 'kubectl delete deployments myapp'
            sh 'kubectl delete deployments mysqldbi'
            sh 'kubectl delete svc mysqldbi-svc'
            sh 'kubectl delete svc myapp-svc'
        }
    }

    stage('Deploying the MySQL container') {
        steps {
            sh 'kubectl apply -f mysql-deployment.yaml'
        }
    }

    stage('Deploying the Web Application container') {
        steps {
            sh 'kubectl apply -f app-deployment.yaml'
        }
    }

}