pipeline {
    agent {label 'BUILD1'}
   parameters { 
    choice(name: 'branch', choices: ['main','devoloper'], description: 'branches')
    string(name: 'build', defaultValue: 'package', description: 'build')
     }
    stages {
        stage('vcs') {
         steps {
            git url: 'https://github.com/rajujaggu/shopizer.git',
            branch: "${params.branch}" 
           }
        }
        stage("build") {
            steps {
                sh "mvn ${params.build}"
            }
        }
        
    }
    agent {label 'PRINT'}
    stages{
        stage('textprinting'){
            steps{
                echo 'Hello World'
            }
        }
    }

}
