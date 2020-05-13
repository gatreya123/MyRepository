node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

        def customImage = docker.build("gatreya/repository_01")

        /* Push the container to the custom Registry */
        customImage.push()
    }

     
    sh "cp -i deployment.yml service.yml /Gourav"
    sh " kubectl create -f deployment.yml"
    sh "kubectl create -f service.yml"
  
}
