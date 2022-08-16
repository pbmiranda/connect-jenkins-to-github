pipeline {
    agent any
    parameters {
        choice(name: 'NUMBER',
            choices: [10,20,30,40,50,60,70,80,90],
            description: 'Select the value for F(n) for the Fibonnai sequence.')
    }
    options {
        buildDiscarder(logRotator(daysToKeepStr: '10', numToKeepStr: '10'))
        timeout(time: 12, unit: 'HOURS')
        timestamps()
    }  
    stages {
        stage('Showing file .bat') {
            steps {
                bat('dir ./scripts/')
            }
        }
        stage('Relative path') {
            steps {
                bat('./scripts/example_windows.bat')
            }
        }
        stage('Full path') {
            steps {
                bat('${env.WORKSPACE}/scripts/example_windows.bat')
            }
        }
        stage('Change directory') {
            steps {
                dir('${env.WORKSPACE}/scripts'){
                    bat('dir')
                }
            }
        }
    }
}
