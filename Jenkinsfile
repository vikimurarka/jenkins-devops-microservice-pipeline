pipeline {
    agent {
        docker { 
            image "csanchez/maven:3-jdk-8-nanoserver-1809"
             args "--entrypoint='' -v C:/Users/muv3kor/.m2:C:/Users/ContainerUser/.m2"
        }
    }
    

    
    stages {
        stage('Test') {
            steps {
               //bat "set"
               bat "mvn clean install"
            }
        }
    }
	post {
		//five types of post action "always","success","failure","unstable","changed"
		always {
			echo 'Post actions after all stage has run'
		}
		success {
			echo 'I run when build is suucessful'
		}
		failure {
			echo 'I run when build fails'
		}
		unstable {
			echo 'when there is a test failue'
		}

		changed{
			echo 'I run only when status of build changes, either from success to fail or vice versa'
		}

	}
}
