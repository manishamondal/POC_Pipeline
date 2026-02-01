pipeline {
    agent any

    parameters {
        string(
            name: 'BRANCH',
            defaultValue: 'main',
            description: 'Git branch'
        )
        choice(
            name: 'ENV',
            choices: ['dev', 'qa', 'prod'],
            description: 'Select environment'
        )
        booleanParam(
            name: 'RUN_TESTS',
            defaultValue: true,
            description: 'Run tests'
        )
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Branch: ${params.BRANCH}"
                echo "Env: ${params.ENV}"
            }
        }
    }
}
