pipeline{
    agent any
     
    stages{
        stage("A"){
            steps{
                sh '''
                    ansible-playbook robot.dryrun.yml -e COMPONENT=mongodb -e ansible_user=centos -e ansible_password=DevOps321 -e ENV=dev
            }
            
        }
    }
}