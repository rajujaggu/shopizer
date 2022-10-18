pipeline {
    agent {label 'OPENJDK-11'}
    triggers {
        pollSCM '30 17 * * *'
    }
    stages {
        stage('pull from vcs') {
         steps {
            git url: 'https://github.com/Qtalha/shopizer.git',
            branch: 'release' 
           }
        }
        stage("build") {
            steps {
                sh 'mvn package'
            }
        }
        stage("merge") {
            steps {
                sh 'git checkout release'
                sh 'git merge --no-ff origin/develop'
            }
        }
    }
}
