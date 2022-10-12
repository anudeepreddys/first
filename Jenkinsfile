pipeline {
    options {
        timeout(time: 1, unit: 'HOURS')
    }

    stages {
        stage('build and push') {
            steps{
                 sh "docker build -t docker/getting-started ."

                withDockerRegistry([url: "", credentialsId: "dockerbuildbot-index.docker.io"]) {
                    sh("docker push docker/getting-started")
                }
            }
        }
    }
}
