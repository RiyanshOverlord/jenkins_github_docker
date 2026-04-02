pipeline{
  agent any
  stages{
    stage('checkout'){
      steps{
        git url:'https://github.com/RiyanshOverlord/jenkins_github_docker.git',branch:'main'
      }
    }
    stage('build image'){
      steps{
        bat 'docker build -t mywebsite .'
      }
    }
      stage('Stop old image'){
        steps{
          bat 'docker stop mycont || exit 0'
          bat 'docker rm mycont || exit 0'
        }
      }
      stage('Runn Image - containerize')
      {
        steps{
          bat 'docker run -d -p 7000:80 --name mycont mywebsite'
        }
      }
    stage('push on hub')
    {
      steps{
        bat 'docker push riyansh7/mywebsite:ver1'
      }
    }
    }
  }


