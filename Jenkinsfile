pipeline {
    agent any
    
     parameters {
                choice(
            name: 'ENVIRONMENT',
            choices: ['DEV', 'QA', 'STAGING'],
            description: 'Select deployment environment'
        )

     }

    stages {
        stage('git hub') {
            steps {
                echo "Git..."
                git 'https://github.com/venkataprabhu11-a11y/boxfuse-sample-java-war-hello.git'
            }
        }
        stage('build') {
            steps {
                echo 'buidling....'
                sh 'mvn compile'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    echo "Selected environment: ${params.ENVIRONMENT}"

                    if (params.ENVIRONMENT == 'DEV') {
                        sh 'echo Deploying to DEV'
                       
                    } else if (params.ENVIRONMENT == 'QA') {
                        sh 'echo Deploying to QA'
                    
                    } else if (params.ENVIRONMENT == 'STAGING') {
                        sh 'echo Deploying to STAGING'
                       
                    } else {
                        error "Invalid environment: ${params.ENVIRONMENT}"
                    }
                }
            }
        }
                    
        stage('test') {
            steps {
                echo 'testing'
                sh 'mvn test'
            }
        }
    }
}
