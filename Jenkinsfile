node {

    stage('SCM Checkout') {
        git branch: 'master', 
        url: 'https://github.com/teten777/my-app'
    }

    stage('Mvn Package'){
	   bat "mvn clean package"
    }

    stage('Email Notification') {
        mail bcc: '', body: 'Your deployment has been success', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'tennugraha777@gmail.com'
    }

}