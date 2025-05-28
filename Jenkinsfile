pipeline{
  agent any

  tools{
    gradle 'Gradle'
    jdk 'JDK'
  }

  stages{
    stage('checkout'){
      steps{
        git branch:'master',url: 'https://github.com/shar4440/MyMavenToGradle18.git'
      }
    }

    stage('initiation'){
      steps{
        sh 'gradle init --type pom'
      }
    }

    stage('Build'){
      steps{
        sh 'gradle build'
      }
    }

    stage('run'){
      steps{
        sh 'java -jar build/libs/MyMavenToGradle18-1.0-SNAPSHOT.jar'
      }
    }
  }

  post{
    success{
      echo "yes"
    }

    failure{
      echo "nooooo!"
    }
  }
}
