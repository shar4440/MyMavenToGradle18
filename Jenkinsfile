pipeline {
    agent any

    tools {
        gradle 'Gradle'   // Ensure this matches the Gradle name in Jenkins Global Tool Configuration
        jdk 'JDK'         // Ensure this matches the JDK name in Jenkins Global Tool Configuration
    }

    environment {
        JAVA_HOME = "${tool 'JDK'}"
        PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/shar4440/MyMavenToGradle18.git'
            }
        }

        stage('Initiation') {
            steps {
                sh 'gradle init --type pom'
            }
        }

        stage('Build') {
            steps {
                sh 'gradle build'
            }
        }

        stage('Run') {
            steps {
                sh 'java -jar build/libs/MyMavenToGradle18-1.0-SNAPSHOT.jar'
            }
        }
    }

    post {
        success {
            echo "✅ Build and run successful!"
        }
        failure {
            echo "❌ Build or run failed!"
        }
    }
}
