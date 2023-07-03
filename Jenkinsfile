pipeline{
    agent any
    environment{                   // Global variable
        SSHCRD          = credentials('SSH_CRD')
         }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
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