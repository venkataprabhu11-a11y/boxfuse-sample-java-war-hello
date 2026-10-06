pipeline {
    agent any

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
