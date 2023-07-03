pipeline{
    agent any
    environment{                   // Global variable
        SSHCRD          = credentials('SSH_CRD')
         }
    parameters {
        string(name: 'COMPONENT', defaultValue: 'mongodb', description: 'Enter the name of the component')
        }
    stages{
        stage("Ansible Lint checks"){
            when{branch pattern: "feature-*", comparator: "REGEXP" }
            steps{
                sh "echo Lint Checks Completed"
            }  
        }    
        stage("Ansible Dry run"){
            steps{
                sh '''
                    echo
                    ansible-playbook robot.dryrun.yml -e COMPONENT=${COMPONENT} -e ansible_user=centos -e ansible_password=${SSHCRD_PSW} -e ENV=dev

                  '''  
            }  
        } 
        stage("Promoting Code to Prod Branch"){
            steps{
                sh "echo Merging the feature branch to PROD branch"
            }  
        }   
        }
 }

            