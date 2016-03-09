node("master") {
    sh "echo $env"
    def flow = dockerFlow.init(
        project: "books-ms",
        scAddress: "http://192.168.99.100:8500",
        target: "app",
        sideTargets: ["db"])
    withEnv([
        "DOCKER_HOST=tcp://192.168.99.100:2376",
        "DOCKER_TLS_VERIFY=0",
        "DOCKER_CERT_PATH=/Users/vfarcic/.docker/machine/machines/docker-flow"
    ]) {
        flow.deploy()
    }
}