pipeline{
    agent any
    tools{
        jdk 'JDK'
        maven 'Maven'
    }
    stages{
        stage('Git Checkout'){
            steps{
                git branch: 'master', url: 'https://github.com/Abionaraji/new-batch.git'
            }
        }
        stage('Build Maven'){
            steps{
                sh 'mvn clean install'
            }
            post{
                success{
                    echo 'now Archiving'
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }
        stage('Unit Test'){
            steps{
                sh 'mvn clean test'
            }
        }
    }
}