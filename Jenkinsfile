pipeline {
    agent any 
    stages {
        stage('DELETION') { 
            steps {
                echo '--REMOVING REPOSITORY IF ALREADY EXIST --'
                sh "sudo rm -rf devops_HelloWorld_jenk"
            }
        }
       stage('CLONE') { 
            steps {
                echo '--CLONE STAGE EXECUTION ---'
    sh "git clone https://github.com/mentorchita/devops_HelloWorld_jenk.git"
            }
        }
        stage('TEST1') { 
            steps {
                echo '--TEST1 STAGE EXECUTION --'
            }
        }
        stage('TEST2') { 
            steps {
                echo '--TEST2 STAGE EXECUTION --'
            }
        }
        stage('BUILD') { 
            steps {
    echo '--BUILD STAGE EXECUTION --'
    sh "node devops_HelloWorld_jenk/index.js"
            }
        }
  stage('DEPLOY') { 
            steps {
    echo '--Finish this PART or deploy app--'
            }
        }
    }
}
