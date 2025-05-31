pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M398"
    }
    // sudo apt update
    // sudo apt install openjdk-21-jdk -y
    // java -version
    // javac -version
    environment {
        JAVA_HOME = '/usr/lib/jvm/java-21-openjdk-amd64'
        PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Echo Version'){
            steps {
                sh 'echo Print Maven VERsion'
                sh 'mvn -version'
            }
        }
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                // git branch: 'main', url: 'https://github.com/lersapho712570/jenkins-hello-world.git'

                // Run Maven on a Unix agent.
                sh "mvn clean package -DskipTests=true"
            }
        }
        stage('Unit Test') {
            steps {
                sh 'mvn test'
            }
        }
    
    }
}
