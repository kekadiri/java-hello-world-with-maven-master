pipeline{
    agent any

  //  tools {
  //       maven 'maven'
  //       jdk 'java'
  //  }

    stages{
        stage('test') {
            steps{
                echo 'file testing'
            }
        }
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github access', url: 'https://github.com/sreenivas449/java-hello-world-with-maven.git']]])
            }
        }
        stage('build'){
            steps{
               sh 'mvn package'
            }
        }
        stage('deploy') {
            steps {
                echo 'deploying'
            }
        }
    }
}
