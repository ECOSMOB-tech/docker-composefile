node{
  stage('git checkout'){
    git url:'', branch:'main'
  }
  stage('connecting another server'){
    sshagent(['Docker_Dev_Server_SSH']) {
    sh 'scp -o StrictHostKeyChecking=no Dockerfile ubuntu@13.234.38.162:'
    sh 'ssh -o StictHostKeyChecking=no ubuntu@13.234.38.162 docker build -t manjuvkp/tomcat .'
    sh 'ssh -o StrictHostKeyCheking=no ubuntu@13.234.38.162 docker run -d -p 8080:8080 --name tomcatserver manjuvkp/tomcat'
    }
  }
}
