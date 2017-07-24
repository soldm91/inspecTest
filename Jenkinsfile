pipeline {
  agent any
  stages {
    stage('Test InSpec') {
      steps {
        echo 'Testing Inspex'
        sh '''mkdir inspecTests
cp -f /var/lib/jenkins/inspecTests/test.rb test.rb
(cd inspecTests; sudo inspec exec test.rb -t ssh://ec2-user@34.228.213.218 -i ~/.ssh/id_rsa)'''
      }
    }
  }
}