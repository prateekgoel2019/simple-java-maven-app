pipeline {

    stages {
        stage('Initialize'){
                def dockerHome = tool 'MyDocker'
                env.PATH = "${dockerHome}/bin:${env.PATH}"
        }
        stage('Build') {
            agent {
                    docker {
                        image 'maven:3-alpine'
                        args '-v /root/.m2:/root/.m2'
                    }
            }
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }

    }
}
