pipeline {
    agent {
      label 'hailinh1'
    }

    environment {
        // Set Maven and Java paths explicitly
        MAVEN_HOME = "/usr/bin/mvn"
        JAVA_HOME = "/usr/lib/jvm/java-17-openjdk-amd64"
        PATH = "${MAVEN_HOME}:${JAVA_HOME}:${env.PATH}"
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Pull latest code'
                sh 'cd /home/ubuntu/CapstoneProjectJavaWeb'
                sh 'git pull origin main'
            }
        }

        stage('Verify Environment') {
            steps {
                echo 'Verifying Java and Maven installation...'
                sh 'java -version'
                sh 'mvn -version'
            }
        }

        stage('Build Application') {
            steps {
                echo 'Building the application with Maven...'
                sh 'cd /home/ubuntu/CapstoneProjectJavaWeb/starter_code && mvn clean package'
            }
        }


        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Replace with your deployment command
                sh 'echo "Deployment step goes here"'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline execution failed!'
        }
    }
}
