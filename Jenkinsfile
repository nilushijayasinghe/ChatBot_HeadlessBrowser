pipeline {
    agent any
    stages{
        stage('Compile Stage'){

            steps {
				sh 'rm -rf chat_bot_rc'
                sh 'git clone https://github.com/nilushijayasinghe/ChatBot_HeadlessBrowser.git chat_bot_headless_rc'
                sh 'cd chat_bot_headless_rc'
                sh 'mvn clean compile'
             }
        }

            stage('Testing stage'){
                steps {
                     sh 'mvn test -Dwebdriver.type=chrome -Dwebdriver.chrome.driver=/home/nilushi/Documents/chatbot/ChatBot_HeadlessBrowser/libs/chromedriver'
                    }
                }

            stage ('Package stage'){
                steps{
                    sh 'mvn package'
                    }
                }

            }

         }