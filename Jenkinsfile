pipeline {
    agent any
    parameters {
        string(name: 'PERSON', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY',  description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD',  description: 'Enter a password')
    }
    stages {
        stage('Example') {
            steps {
                echo "Hello ${params.PERSON} and ${env.NODE_NAME}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
            }
        }
    }
}
