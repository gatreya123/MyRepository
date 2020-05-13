node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

        def customImage = docker.build("gatreya/repository_01")

        /* Push the container to the custom Registry */
        customImage.push()
    }

     
    sh "sudo cp -i deployment.yml service.yml /Gourav"
    sh "sudo  kubectl create -f deployment.yml"
    sh "sudo kubectl create -f service.yml"
  
}
