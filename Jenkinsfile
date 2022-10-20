pipeline {
    agent {label 'LABEL-1'}
   triggers { pollSCM('* * * * *') }
    stages {
        stage('vcs') {
         steps {
            git url: 'https://github.com/rajujaggu/shopizer.git',
            branch: 'devoloper' 
           }
        }
        stage("build") {
            steps {
                
                sh 'mvn package'
            }
        }
        
    }
}
