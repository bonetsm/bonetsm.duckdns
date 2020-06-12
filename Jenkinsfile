pipeline {
    agent {
        label 'docker-slave'
    }
    stages {
        stage('pull') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], 
                    userRemoteConfigs: [[credentialsId: 'bonetsm-github', url: 'https://github.com/bonetsm/bonetsm.duckdns.git']]])
            }
        }
        stage('build') {
            steps {
                withCredentials([string(credentialsId: 'duckdns_token', variable: 'duckdns_token'),string(credentialsId: 'duckdns_domain', variable: 'duckdns_domain')]) {
                    ansiblePlaybook extras: "-e duckdns_token=${duckdns_token} -e duckdns_domain=${duckdns_domain}", playbook: 'duckdns.yml'
                }
            }
        }
        stage ('test') {
            steps {
                echo 'test'
            }
        }
        stage ('deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
}
