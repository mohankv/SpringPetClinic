pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3.6.3"
    }

    stages {
        stage('checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/mohankv/SpringPetClinic.git'
            }
        }
        stage("build") {
            steps {
                sh "mvn compile"
            }
        }
        stage("test") {
            steps {
                sh "mvn test"
            }
        }
        stage("package") {
            steps {
                sh "mvn package"
            }
        }
        stage("deploy") {
            steps {
                sh "java -jar /home/coder/.jenkins/workspace/petClinicDeclarativePipeline/target/spring-petclinic-2.1.0.BUILD-SNAPSHOT.jar"
            }
        }
    }
}
