pipeline {
  agent any
  stages {
    stage('copy script file') {
      steps {
        sh '''ansible vultr -m copy -a "src=/root/install-nginx.sh dest=/root"
'''
      }
    }
    stage('exec script to install nginx') {
      steps {
        sh 'ansible vultr -m shell -a "bash /root/install-nginx.sh"'
      }
    }
    stage('start nginx') {
      steps {
        sh '''ansible vultr -m shell -a "exec nginx"
ansible vultr -m shell -a "ss -tnlp"'''
      }
    }
  }
}