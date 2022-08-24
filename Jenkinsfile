pipeline {
	agent any
	stages {
	stage('Build') {
	steps {
		sh "rm -rf jenkins"
		sh "git clone https://github.com/lejumoh/jenkins.git"
	}
	}
	stage ('may') {
	steps {
		sh "cd jenkins && ls git branch"

	}
	}
	stage ('package') {
	steps {
		sh "cd jenkins && docker build -t webserver ."

	}
	}
		stage ('deploy') {
	steps {
		sh "cd jenkins && docker stop webserver || true && docker rm webserver || true && docker run -d -p 80:80 --name webserver:latest"
		
	}
	}
}
}

