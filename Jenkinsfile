pipeline {
  agent any
  stages {
    stage ("CLONE") {
      steps {
        echo "Clone phase started..."
        sh """
        hostname
        git pull https://github.com/NagihanVural/helloworld.git
        """
      }
    }
    stage ("BUILD") {
      steps {
        echo "Build phase started..."
        sh """
        hostname
        docker build -t nagihanvural/python-web-app:latest .
        """
      }
      
      }
      stage ("PUSH") {
        steps{
          echo "Push phase started..."
          sh """
          hostname
          
          docker push nagihanvural/python-web-app:latest
          """
        }
      
      }
      stage ("DEPLOY") {
        steps {
          echo "Deploy phase started..."
          sh """
          
          """
        }
      }
  }
  
}
