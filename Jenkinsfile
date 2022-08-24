pipeline {
	agent any 
	stages {
    stage(‘Build’) {
	steps {
		sh "rm -rf nginx"
        sh "git clone https://github.com/lejumoh/jenkins.git"
	}
	}
	stage (‘Test’) {
	steps {
		sh "cd jenkins && ls && git branch"
	
	}
	}
    stage (‘Package’) {
	steps {
		sh "cd jenkins && docker build -t webserver  ."

	}
	}
        stage (‘deploy’) {
	steps {
		sh "cd jenkins && docker stop webserver || true && docker rm webserver || true && docker run -d -p 80:80 --name webserver webserver:latest"

	}
	}
}
}



