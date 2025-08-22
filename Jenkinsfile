node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', url: 'https://github.com/smbyun0214/docker-ci-demo.git'
    }

    stage('Build image') {
       dockerImage = docker.build("smbyun0214/web_count:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
