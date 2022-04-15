pipeline {
  agent any
  stages {
    stage('packer_aws_login'){
      steps{
        script{
          withCredentials([file(credentialsId: 'PACKER_VARS', variable: 'packerVars')]){
            sh "cp -f \$packerVars /var/lib/jenkins/workspace/IaC/AMI/vars.json"
          }
        }
      }
    }
    stage('packer_version'){
      steps{
        script{
          sh "packer version"
        }
      }
    }
    stage('packer_build'){
      steps{
        script{
          sh "echo "starting build...""
          sh "packer build -var-file=vars.json template.json"
        }
      }
    }
  }
}
