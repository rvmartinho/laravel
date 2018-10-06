node('php'){
    stage('Clean'){
        deleteDir()
        sh 'ls -la'
    }

    stage('Fetch') {
        checkout scm
    }

    stage('Docker Build') {
        sh 'docker build -t rvmartinho/laravel:$BUILD_NUMBER .'
    }

    stage('Docker Ship') {
        sh 'docker push rvmartinho/laravel:$BUILD_NUMBER'
    }
    
    stage('Docker Clean') {
        sh 'docker rmi -f rvmartinho/laravel:$BUILD_NUMBER'
    }
}
