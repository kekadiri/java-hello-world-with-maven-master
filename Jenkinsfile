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
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github access', url: 'https://github.com/kekadiri/java-hello-world-with-maven-master.git']]])
            }
        }
        stage('build'){
            steps{
               sh 'mvn clean package'
            }
        }
        stage('deploy') {
            steps {
                echo 'deploying'
            }
        }
    }
}
