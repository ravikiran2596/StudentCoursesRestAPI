pipeline {
    agent { label 'dockeragent' }
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git url: '',
                    branch: 'develop'
            }
        }
        stage('build') {
            steps {
                sh 'docker image build -t ravikiran2596/spc:latest .'
            }
        }
        stage('scan and push') {
            steps {
                sh 'echo docker scan ravikiran2596/spc:latest'
                sh 'docker image push ravikiran2596/spc:latest'
            }
        }
    }

}
