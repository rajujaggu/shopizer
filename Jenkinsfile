pipeline {
    agent {label 'BUILD1'}
   parameters { 
    choice(name: 'branch', choices: ['master','devoloper'], description: 'branches')
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
        stage('textprinting'){
             agent {label 'PRINT'}
             steps{
                echo 'Hello World'
             }
            
        }
        
    }
   

}