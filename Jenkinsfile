pipeline {
    agent any

    stages {
        stage('Checkout') {
                    steps {
                        git branch: 'main', url: 'https://github.com/elavazhaganthirumalai/springboot-backend'
                    }
                }

                stage('Build') {
                    steps {
                        bat 'mvn clean install'
                    }
                }

        stage('Run') {
            steps {
                withEnv ( ['JENKINS_NODE_COOKIE=do_not_kill'] )
                {
                bat 'start java -jar target/*.jar&'
                }

            }
        }
    }
}
