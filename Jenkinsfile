node {
    
    stage('SCM Checkout') {
        git branch: 'master', 
        url: 'https://github.com/teten777/my-app'
    }

    stage('Mvn Package'){
	   bat "mvn clean package"
    }

    stage('Sonarqube Analysis'){
        withSonarQubeEnv('sonarqube-local') { 
          bat "mvn sonar:sonar"
        }
	   
    }	

    stage('Upload war to nexus'){
        script {
            nexusArtifactUploader artifacts: [
                    [
                        artifactId: 'myweb', 
                        classifier: '', 
                        file: 'target/my-app-0.0.7-SNAPSHOT.war', 
                        type: 'war'
                    ]
                ], 
            credentialsId: 'nexus3', 
            groupId: 'in.javahome', 
            nexusUrl: 'localhost:8083', 
            nexusVersion: 'nexus3', 
            protocol: 'http', 
            repository: 'simpleapp-release', 
            version: '1.0.0'
        }
    }	

    stage('Email Notification') {
        mail bcc: '', body: 'Your deployment has been success', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'tennugraha777@gmail.com'
    }

}
