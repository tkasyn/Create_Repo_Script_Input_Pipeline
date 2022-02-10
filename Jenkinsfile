pipeline {
    agent any
    environment {
        GITHUB_TKN = credentials('7483dec3-81dc-40b6-9b62-49bce24ad193')
    }
    stages {
       stage ('Build') {
                agent any
                //environment {
                 //   GITHUB_TOKEN = "$GITHUB_TKN"
                //}
                    steps {
                         //withCredentials([string(credentialsId: '7483dec3-81dc-40b6-9b62-49bce24ad193', variable: 'GITHUB_TKN')]) {
                         // sh 'sudo chmod +x ./create_repository_git.sh'
                         sh "chmod +x -R ${env.WORKSPACE}"
                         sh './create_repository_git.sh'  
                         //}
                    }
       }
    }
}
