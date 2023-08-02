podTemplate(label: 'docker-bitcoin-abc', containers: [
  containerTemplate(name: 'docker', image: 'docker', ttyEnabled: true, command: 'cat', envVars: [
    envVar(key: 'DOCKER_HOST', value: 'tcp://docker-host-docker-host:2375')
  ])
]) {
  node('docker-bitcoin-abc') {
    stage('Build Image') {
      container('docker') {
        def scmVars = checkout scm
        def VERSION = "bchn-26.1"
        def VERSION_MINOR = "${VERSION}.0"
        dir("${VERSION}") {
          sh "docker build -t santiment/bitcoin-abc:${VERSION_MINOR} -t santiment/bitcoin-abc:${VERSION} ."

          withDockerRegistry([ credentialsId: "dockerHubCreds", url: "" ]) {
            sh "docker push santiment/bitcoin-abc:${VERSION_MINOR}"
            sh "docker push santiment/bitcoin-abc:${VERSION}"
          }
        }
      }
    }
  }
}
