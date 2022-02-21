node{
  stage('git checkout'){
    git url: 'https://github.com/ECOSMOB-tech/docker-composefile.git', branch: 'main'
  }
  stage('connecting another server'){
    sshagent(['Docker_Dev_Server_SSH']) {
    sh 'scp -o StrictHostKeyChecking=no Dockerfile ubuntu@13.234.38.162:'
    sh 'ssh -o StrictHostKeyChecking=no  ubuntu@13.234.38.162 sudo chmod -R 665 /var/run/docker.sock'  
    sh 'ssh -o StrictHostKeyChecking=no ubuntu@13.234.38.162 docker build -t manjuvkp/tomcat .'
    sh 'ssh -o StrictHostKeyChecking=no ubuntu@13.234.38.162 docker run -d -p 8080:8080 --name tomcatserver manjuvkp/tomcat'
    }
  }
}
