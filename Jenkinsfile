pipeline{
	agent any
	stages{
		stage('checkout'){
			steps{
				echo "Cloning repo.."
				git url:"https://github.com/Deekshitha-m29/Exam1202.git",branch:'main'
			}
		}
		stage('Build'){
			steps{
				echo "Build Docker Image"
				bat "docker build -t myapp ."
			}
		}
		stage('Run'){
			steps{
			echo "RUN application in Docker Container"
			bat "docker rm -f myContainer || exit0"
			bat "docker run -d -p 5000:5000 --name myContainer myapp"

		}
	}

	}
post{
	success{
		echo 'pipleline completed successfully!'
	}
	failure{
		echo 'pipeline failed'
	}
	}

}

