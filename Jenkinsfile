node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

        def customImage = docker.build("gatreya/repository_01")

        /* Push the container to the custom Registry */
        customImage.push()
    }

                   def image_id = registry + ":$BUILD_NUMBER"
                   sh "ansible-playbook  playbook.yml --extra-vars \"image_id=${image_id}\""
              
           
}
