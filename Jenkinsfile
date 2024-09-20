pipeline {
    agent any

    stages {
        stage('Input Environment') {
            steps {
                script {
                    env.SELECTED_ENV = input(
                        id: 'EnvironmentInput', 
                        message: 'Select the environment to proceed', 
                        parameters: [
                            choice(name: 'ENVIRONMENT', choices: ['Production', 'Development', 'Test'], description: 'Choose the environment')
                        ]
                    )
                }
            }
        }

        stage('Print Message for Selected Environment') {
            when {
                expression { env.SELECTED_ENV == 'Production' }
            }
            steps {
                echo 'You have selected the Production environment!'
            }
        }

        stage('Print Message for Development') {
            when {
                expression { env.SELECTED_ENV == 'Development' }
            }
            steps {
                echo 'You have selected the Development environment!'
            }
        }

        stage('Print Message for Test') {
            when {
                expression { env.SELECTED_ENV == 'Test' }
            }
            steps {
                echo 'You have selected the Test environment!'
            }
        }
    }
}
