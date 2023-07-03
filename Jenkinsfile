pipeline{
    agent any
    environment{                   // Global variable
        SSHCRD          = credentials('SSH_CRD')
         }
    parameters {
        string(name: 'COMPONENT', defaultValue: 'mongodb', description: 'Enter the name of the component')
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