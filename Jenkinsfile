@Library('defra-library@v-9') _

def validateClosure = {
  stage('Add Abaco container registry') {
    withCredentials([
      usernamePassword(credentialsId: 'abaco-docker-registry', usernameVariable: 'username', passwordVariable: 'password')
    ]) {
      ctx.sh("helm repo add --force-update $repoName $ABACO_DOCKER_REGISTRY --username $username --password $password")
      ctx.sh('helm repo update')
    }
  }
}

buildHelm validateClosure: validateClosure
