pipeline {
    agent any
    parameters {
        gitParameter branchFilter: 'origin/(.*)', defaultValue: 'main', name: 'BRANCH', type: 'PT_BRANCH'
//         string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//         text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
//         booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
//         choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
//         password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Choose branch name') {
            steps {
                git branch: "${params.BRANCH}", url: 'https://github.com/PatkaLip/aplikacja_kalkulator_tdd.git'
            }
        }
        stage('Choose smoke/regression/nightly') {
            steps {
                echo 'TODO'
            }
        }
        stage('Test') {
            steps {
                sh 'python3.8 -m pylint ---html=pylint_report.html'
                sh 'python3.8 -m pytest --html=report.html'
                archiveArtifacts artifacts: 'report.html, assets', followSymlinks: false
            }
            
            
            
        }
    }
}
