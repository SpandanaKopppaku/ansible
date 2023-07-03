pipeline{
    agent any
      environment{
        ENv_URL         = "pipeline.google.com"                    // Global variable
        SSHCRD          = credentials('SSH_CRD')
         }
    stages{
        stage("A"){
            steps{
                sh '''
                    ansible-playbook robot.dryrun.yml -e COMPONENT=${COMPONENT} -e ansible_user=centos -e ansible_password=${SSHCRED_PSW} -e ENV=dev
            }
            
        }
    }
}