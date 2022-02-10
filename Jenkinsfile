pipeline {
    agent any
    environment {
        GITHUB_TKN = credentials('7483dec3-81dc-40b6-9b62-49bce24ad193')
    }
    stages {
        
       stage ("Promt for Input Value") {
            steps {
                script {
                    REP_NAME = input message: 'Please enter a new Repository Name',
                             parameters: [string(defaultValue: '',
                                          description: 'Repository Name',
                                          name: 'Repository_Name')]
                }
                        echo "Repository ${REP_NAME} will be created"
            }
        }
              
       stage ('Build') {
                agent any
                environment {
                    REPO_NAME = "${REP_NAME}"
                }
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
