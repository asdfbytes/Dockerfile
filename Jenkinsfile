pipeline{
  agent any
    stages{
      stage('Checkout'){
        steps{
          git 'https://github.com/asdfbytes/Dockerfile.git'
        }
      }
      stage('PBuild Image'){
        steps{
          bat 'docker build -t mywebsite.'
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
