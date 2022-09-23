node {
    def app
     stage('Clone-checkout'){
        checkout scm
     }
     stage('Build image'){
        app = docker.build("jenkins/httpd")
     }
     stage ('Test'){
        withDockerContainer("jenkins/httpd"){ 
            sh "echo 'Bonjour'" 
            }
            }
}
