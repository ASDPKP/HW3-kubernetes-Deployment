pipeline {
    stage('Cleaning the cluster') {
        steps {
            sh 'kubectl delete deployments myapp'
            sh 'kubectl delete deployments mysqldbi'
            sh 'kubectl delete svc mysqldbi-svc'
            sh 'kubectl delete svc myapp-svc'
        }
    }
}