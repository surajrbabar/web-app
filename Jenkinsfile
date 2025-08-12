pipeline{
  agent any
  stages{
    stage("build image"){
      steps{
        echo "Building the docker image"
        withCredentials([usernamePassword(credentialsId : "dockerhub-credentials", usernameVariable : "USER", passwordVariable : "PASS")]){
          sh 'docker build -t surajrbabar/java-maven-app:web-1.0 .'
          sh 'echo $PASS | docker login -u $USER --password-stdin'
          sh 'docker push surajrbabar/java-maven-app:web-1.0'
        }
      }
    }
  }
}
