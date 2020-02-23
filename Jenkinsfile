pipeline {
    agent any
    tools {
        maven 'Maven'
    }
    stages{
        stage('Build'){
            steps{
                 sh script: 'mvn clean package'
            }
        }
        stage('Upload War To Nexus'){
            steps{
                 nexusArtifactUploader artifacts: [
                     [
                        artifactId: 'simple-app',
                        classifier: '', 
                        file: 'target/simple-app-1.0.0.war', 
                        type: 'war'
                 ]
              ],
             credentialsId: '9c9686c1-ab14-45dd-b56d-405e19770f47',
             groupId: 'in.javahome',
             nexusUrl: 'localhost:8081',
             nexusVersion: 'nexus3',
             protocol: 'http',
             repository: 'Simpleapp.release',
             version: '1.0.0'


            }
        }
    }
}
