pipeline {
    agent any 
    environment {
        NODE_VERSION = '14.17.0' // Задайте потрібну версію Node.js
    }
    stages {
        stage('Setup') {
            steps {
                echo '--ВСТАНОВЛЕННЯ NODE.JS ЗА ДОПОМОГОЮ NVM--'
                sh 'curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash'
                sh 'export NVM_DIR="$HOME/.nvm"'
                sh '[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm'
                sh '[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion'
                sh "nvm install ${NODE_VERSION}"
                sh "nvm use ${NODE_VERSION}"
            }
        }
        stage('DELETION') {
            steps {
                echo '--ВИДАЛЕННЯ РЕПОЗИТОРІЮ ЯКЩО ВІН ВЖЕ ІСНУЄ --'
                sh "sudo rm -rf HW_Jenk"
            }
        }
        stage('CLONE') {
            steps {
                echo '--ВИКОНАННЯ ЕТАПУ КЛОНУВАННЯ ---'
                dir('HW_Jenk') {
                    sh "git clone https://github.com/obodniak/HW_Jenk.git ."
                }
            }
        }
        stage('TEST1') {
            steps {
                echo '--ВИКОНАННЯ ЕТАПУ ТЕСТУВАННЯ 1 --'
            }
        }
        stage('TEST2') {
            steps {
                echo '--ВИКОНАННЯ ЕТАПУ ТЕСТУВАННЯ 2 --'
            }
        }
        stage('BUILD') {
            steps {
                echo '--ВИКОНАННЯ ЕТАПУ ПОБУДОВИ --'
                sh "node HW_Jenk/index.js"
            }
        }
        stage('DEPLOY') {
            steps {
                echo '--ЗАВЕРШЕННЯ ЦЬОГО ЕТАПУ АБО РОЗГОРТАННЯ ДОДАТКУ--'
            }
        }
    }
}
