node {

   stage('Checkout') {

   checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/mayankbatra123/snappass']]])
   
   }
   stage('Docker build Image') {
   
   sh 'export SNAPPASS_NGINX_GIT_SHA=$(git rev-parse HEAD)'
   sh 'docker build -t mayankbatra123/snappass:$SNAPPASS_NGINX_GIT_SHA'
   sh 'docker push mayankbatra123/snappass:$SNAPPASS_NGINX_GIT_SHA'

   }
   stage('Results') {
   
   echo Hello

   }
}
