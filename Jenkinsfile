pipeline{
     agent any
     environment {
            DOCKERHUB_CREDENTIALS=credentials('bastien')
      }
      stages {
            stage('git clone') {
                 steps {
                      git branch: 'main', url: 'https://github.com/bstcoudray/jenkins/'
                    }
                 }
              stage('build') {
                      steps {
                         sh 'docker build -t  bastiencoudray/ipssi-httpd:latest . '
                    }
                 }
             stage('login') {
                      steps {
                         sh 'echo $DOCKERHUB_CREDENTIALS_PSW  | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                    }
                 }
            stage('push') {
                 steps {
                      sh 'docker push bastiencoudray/ipssi-httpd:latest'
                    }
                  }
                }
            post {
                always {
                      sh 'docker logout'
                   }
                 }
}
