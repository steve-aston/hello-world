pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        svn(url: 'https://subversion.apt.fs.fujitsu.com/svn/repository/POA/poa-bal/branches/poa-bal-auto', poll: true)
      }
    }
    stage('Build') {
      steps {
        build(job: 'POA_Pipe_1', quietPeriod: 1, wait: true)
      }
    }
    stage('Deploy') {
      steps {
        sh '/vr/lib/test.sh'
      }
    }
  }
}