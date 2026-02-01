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
        checkout([
            $class: 'GitSCM',
            branches: [[name: "*/${params.BRANCH}"]],
            userRemoteConfigs: [[
                url: 'https://github.com/manishamondal/POC_Pipeline/',
                credentialsId: 'github_pat'
            ]]
        ])
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
