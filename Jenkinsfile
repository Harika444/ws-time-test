node
  {                   
    stage ('Workspace Cleanup') {
      cleanWs()                             
    }
    stage('Code Checkout')
    {
        git url: 'https://github.com/Harika444/ws-time.git'
    }     
    stage('Build'){       
            sh label: '', script: '''
            auth_token=`aws codeartifact get-authorization-token --domain daxeos --query authorizationToken --output text --duration-seconds 900 --region us-west-2`
            docker build -t knagu/websocket:$BUILD_NUMBER --build-arg TOKEN=$auth_token .
	          docker build -t knagu/websocket:$BUILD_NUMBER --build-arg TOKEN=$auth_token .
            '''
            echo "Build Succcessful"                   
    }
  }
