pipeline
{
  agent any
  tools{
    maven 'Maven3.6.3'
  }
  stages{
    stage('SCM Checkout')
    {
      steps
      {
        git 'https://github.com/Jeevitha38/tcsion'
      }
    }
    stage('Compiler-Package')
    {
      steps
      {
        sh "mvn -version"
        sh "mvn clean install"
        sh "mvn package"
      }
    }
  }
  post
  {
    always{
      cleanWs()
    }
  }
}
