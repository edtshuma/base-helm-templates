pipeline {
    agent any
    triggers {
        githubPush()
    }

    environment { 
    PROJECT_NAME = "base-helm-templates"
}
    stages {

        stage('Checkout'){
           steps{
               sh "echo  ${PROJECT_NAME}"
            }
         }

      }
}
 
