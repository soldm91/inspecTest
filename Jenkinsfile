pipeline {
  agent any
  stages {
    stage('Test InSpec') {
      steps {
        echo 'Testing Inspex'
        sh '''cp -f /var/lib/jenkins/inspecTests/test.rb test.rb
sudo inspec exec test.rb -t ssh://ec2-user@34.228.213.218 -i /home/ec2-user/.ssh/id_rsa'''
      }
    }
  }
}