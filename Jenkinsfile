pipeline {
    agent any 
    stages {
        stage('Check Node.js') {
            steps {
                script {
                    def nodeVersion = sh(script: 'node -v', returnStdout: true).trim()
                    if (nodeVersion) {
                        echo "Node.js is already installed: ${nodeVersion}"
                    } else {
                        echo "-- Node.js is not installed --"
                        echo "-- INSTALLING NVM --"
                        sh "curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash"
                        sh "source ~/.bashrc"
                        sh "nvm install 14.18.1" // Встановлюємо конкретну версію Node.js
                    }
                }
            }
        }
        stage('DELETION') {
            steps {
                echo '-- REMOVING REPOSITORY IF ALREADY EXISTS --'
                sh "sudo rm -rf HW_Jenk"
            }
        }
        stage('CLONE') {
            steps {
                echo '-- CLONE STAGE EXECUTION --'
                dir('HW_Jenk') {
                    sh "git clone https://github.com/obodniak/HW_Jenk.git ."
                }
            }
        }
        stage('TEST1') {
            steps {
                echo '-- TEST1 STAGE EXECUTION --'
            }
        }
        stage('TEST2') {
            steps {
                echo '-- TEST2 STAGE EXECUTION --'
            }
        }
        stage('BUILD') {
            steps {
                echo '-- BUILD STAGE EXECUTION --'
                sh "node index.js" // Виконуємо ваш скрипт після встановлення Node.js
            }
        }
        stage('DEPLOY') {
            steps {
                echo '-- Finish this PART or deploy app --'
            }
        }
    }
}