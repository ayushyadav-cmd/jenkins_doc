pipeline{
	agent any

	enviroment{
		DOCKER_IMAGE = 'hello-world:latest' 
		}	
		stages{
			stage('Checkout'){
				steps{
					git branch:'main' , url:'https://github.com/ayushyadav-cmd/jenkins_doc.git'
					}
			}
		stage('Docker Build'){
			steps {
				script{
					if (fileExists('Dockerfile')){
					sh "docker build -t ${env.DOCKER_NAME} ."
					} else{
						error "Dockerfile not found in the workspace.Please create one for your python application."
					}
					}	
					}
					}	

		stage('Docker Run (Optional)'{
			steps{
				sh "docker run --rm ${env.DOCKER_IMAGE}"
}
}

		post {
			success{
				echo'success'
}
			failure {
				echo'failure'
}
}
}
