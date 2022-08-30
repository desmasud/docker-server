pipeline {
    agent any
environment {
  AWS_ACCESS_KEY_ID = credentials('AWS_credential')
  
}
    stages {
  stage('git checkout') {
    steps {
     git branch: 'main', url: 'https://github.com/desmasud/docker-server.git'
    }
  }
  stage("terraform init") {
    steps {
        sh 'terraform init'
    }
  }
stage("terraform plan") {
    steps {
        sh 'terraform plan'
    }
  }
  stage("terraform destroy") {
    steps {
        sh 'terraform destroy -auto-approve'
    }
  }
}

}
