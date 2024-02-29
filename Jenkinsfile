pipeline {
    agent any
        stages {
       // stage('Checkout') {
         //   steps {
           //     git 'https://github.com/kekadiri/java-hello-world-with-maven-master.git'
            //}
        //}
            stage('build') {
                steps {
                    sh 'mvn clean package'
                }
            }
            
            stage('sonar') {
                steps {
                   sh 'mvn sonar:sonar'
                }    
            }
            stage('Deploy to Nexus') {
            steps {
                nexusArtifactUploader(
                    nexusVersion: 'nexus3',
                    protocol: 'http',
                    nexusUrl: '54.91.254.146:8081',
                    groupId: 'pom.org.springframework',
                    version: 'pom.0.2.1',
                    repository: 'maven-releases',
                    credentialsId: 'nexus',
                    artifacts: [
                        [artifactId: 'jb-hello-world-maven',
                         file: 'target/jb-hello-world-maven-0.2.1.jar',
                         type: 'jar']
                    ]
                    )
                }
            }
        }
}
