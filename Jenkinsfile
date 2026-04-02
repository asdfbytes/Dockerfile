pipeline{
  agent any
    stages{
      stage('Checkout'){
        steps{
          git url:'https://github.com/asdfbytes/Dockerfile.git',branch: 'main'
        }
      }
      stage('Build Image'){
        steps{
          bat 'docker build -t mywebsite .'
        }
      }
      stage('stop old Containers'){
        steps{
          bat 'docker stop myacont || exit 0'
          bat 'docker rm mycont || exit 0'
        }
      }
      stage ('Run Image - Container'){
        steps{
          bat 'docker run -d -p 7000:80 --name mycont mywebsite'

                            }
                  }
        }
}
