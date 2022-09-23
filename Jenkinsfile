node {
    def app
     stage('Clone-checkout'){
        checkout scm
     }
     stage('Build image'){
        app = docker.build("jenkins/apache")
     }
     stage ('Test'){
        withDockerContainer("jenkins/nginx"){ 
            sh "echo 'Bonjour'" 
            }
            }
}
