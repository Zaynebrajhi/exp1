pipeline {
    agent any
tools{
    maven 'maven'
}
    stages {
        stage("clean up") {
            steps {
                echo deleteDir()
            }
        }
   
   
        stage("clone repo") {
            steps {
                sh "git clone https://github.com/Zaynebrajhi/exp1"

            }
        }
   

        stage("Generate backend image") {
            steps {
                dir ("exp1/backend-master"){
                    sh "mvn clean install"
                    sh "docker build -t backend-master ."
                }
            }
        }
   
   
        stage("Run docker compose") {
            steps {
                dir("exp1/backend-master"){
                sh "docker compose up -d"
            }
        }
    }  
}
}
