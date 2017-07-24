pipeline {
  agent any
  stages {
    stage('Create subnet') {
      steps {
        echo 'creating subnet'
        sh '''(cd /var/lib/jenkins/terraformPractice/; sudo git pull)
cp -f /var/lib/jenkins/variables/variables.tf variables.tf
cp -f /var/lib/jenkins/terraformPractice/newSubnet.tf newSubnet.tf
terraform init
terraform plan
terraform apply'''
      }
    }
    stage('Sleep 3 Minutes') {
      steps {
        echo 'Sleeping'
        sleep(time: 3, unit: 'MINUTES')
        echo 'done sleeping'
      }
    }
    stage('Destroy') {
      steps {
        echo 'destroying'
        sh 'terraform destroy -force || true'
      }
    }
  }
}
