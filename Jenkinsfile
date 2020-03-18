node {
    stage('SCM Checkout') {
        git 'https://github.com/teten777/my-app'
    }
    stage('Compile-Package') {
        sh 'mvn clean package'
    }
}