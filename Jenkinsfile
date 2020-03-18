node {

    stage('SCM Checkout') {
        git branch: 'master', 
        url: 'https://github.com/teten777/my-app'
    }

    stage('Mvn Package'){
	   sh "mvn clean package"
   }
}