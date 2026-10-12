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
        stage('deploy') {
            steps {
                echo "Deploying to ${params.ENVIRONMENT}"
                echo 'deploying....'
                sh 'mvn install'
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
