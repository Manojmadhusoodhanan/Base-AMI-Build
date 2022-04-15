pipeline {
  agent any
  stages {
    stage('aws_login'){
      steps{
        script{
          withCredentials([file(credentialsId: 'PACKER_VARS', variable: 'packerVars')]){
            sh "cp -f \$packerVars /var/lib/jenkins/workspace/IaC/AMI/vars.json"
            sh "cat /var/lib/jenkins/workspace/IaC/AMI/vars.json"
          }
        }
      }
    }
  }
}
