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
			credentialsId: 'nexus1',
			groupId: 'javahome',
			nexusUrl: '52.66.206.178:8081',
			nexusVersion: 'nexus2',
			protocol: 'http',
			repository: 'simple.repositorie',
			version: '1.0.0'


            }
        }
    }
}
