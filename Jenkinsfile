pipeline {
    agent any 
    stages {
        stage('DELETION') { 
            steps {
                echo '--REMOVING REPOSITORY IF ALREADY EXIST --'
                sh "sudo rm -rf HW_Jenk"
            }
        }
        stage('CLONE') {
            steps {
                echo '--CLONE STAGE EXECUTION ---'
                sh "git clone https://github.com/obodniak/HW_Jenk.git"
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
                sh "node \$(pwd)/HW_Jenk/index.js"
            }
        }
        stage('DEPLOY') {
            steps {
                echo '--Finish this PART or deploy app--'
            }
        }
    }
}