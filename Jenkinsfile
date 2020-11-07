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
          export AWS_ACCESS_KEY_ID=\$(aws configure get default.aws_access_key_id)
          export AWS_SECRET_ACCESS_KEY=\$(aws configure get default.aws_secret_access_key)
          export AWS_DEFAULT_REGION=us-east-2
          sudo terraform init
          sudo terraform plan
          sudo terraform apply -auto-approve
          """
        }
      }
  }
  
}
