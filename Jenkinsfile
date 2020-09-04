pipeline {
        agent any
    stages {
        stage('Create kubernetes cluster') {
            steps {
                withAWS(region:'us-west-2', credentials:'aws-static'){
                    sh '''
                        eksctl create cluster -f cluster.yaml
                    '''
                }
            }
        }
        stage('Create conf file cluster') {
            steps {
                withAWS(region:'us-west-2', credentials:'aws-static'){
                    sh '''
                        aws eks --region us-west-2 update-kubeconfig --name CapstoneCluster
                    '''
                }
            }
        }
    }
}
