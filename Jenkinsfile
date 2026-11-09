pipeline{
    agent any
    stages{
        stage('Build docker image'){
            steps{
                echo "Building docker image"
                bat 'docker build -t mypythonappflask .'
            }
        }
        stage('Run docker image'){
            steps{
                echo "Running docker image"
                bat 'docker rm -f mypythonappflask || exit 0'
                bat 'docker run -d -p 5001:5001 --name mypythonappflask'
            }
        }
    }
    post{
        success{
            echo "The docker,build and run is successful"
        }
        failure{
            echo "The docker build and run is failed"
        }
    }
}