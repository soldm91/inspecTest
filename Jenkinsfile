pipeline {
  agent any
  stages {
    stage('Test InSpec') {
      steps {
        parallel(
          "Test listening 8080": {
            echo 'Testing Inspex'
            sh '''cp -f /var/lib/jenkins/inspecTests/test.rb test.rb
sudo inspec exec test.rb -t ssh://ec2-user@172.31.23.255 -i /home/ec2-user/.ssh/id_rsa'''
            
          },
          "Test Hostname": {
            sh '''cp -f /var/lib/jenkins/inspecTests/hostname.rb hostname.rb
sudo inspec exec hostname.rb -t ssh://ec2-user@172.31.23.255 -i /home/ec2-user/.ssh/id_rsa'''
            
          },
          "Test DNS": {
            sh '''cp -f /var/lib/jenkins/inspecTests/dns.rb dns.rb
sudo inspec exec dns.rb -t ssh://ec2-user@172.31.23.255 -i /home/ec2-user/.ssh/id_rsa'''
            
          },
          "Test Resolv": {
            sh '''cp -f /var/lib/jenkins/inspecTests/resolv.rb resolv.rb
sudo inspec exec resolv.rb -t ssh://ec2-user@172.31.23.255 -i /home/ec2-user/.ssh/id_rsa'''
            
          },
          "Test eth0": {
            sh '''cp -f /var/lib/jenkins/inspecTests/eth0.rb eth0.rb
sudo inspec exec eth0.rb -t ssh://ec2-user@172.31.23.255 -i /home/ec2-user/.ssh/id_rsa'''
            
          }
        )
      }
    }
  }
}