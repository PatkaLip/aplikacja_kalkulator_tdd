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
        stage('Example Test') {
            steps {
                echo 'Hello, JDK'
            }
        }
    }
}
