node('HelloWorldAgent'){
    stage 'get mvn version'
    sh 'mvn -v'
}

node('HelloWorldAgent'){

   stage 'Stage 1 - SCM'
   echo 'get HelloWorld_Java from github'
   git url: 'https://github.com/sunbeltdn/HelloWorld_Java.git'

   input 'ready to package and run?'


   stage 'Stage 2 - clean'
   sh 'export JENKINS_HOME=/home/jenkins/jenkins_agent'
   sh 'cd $JENKINS_HOME/workspace/helloWorld'
   echo 'mvn clean'
   sh 'mvn clean'

   stage 'Stage 3 -package'
   sh 'mvn package'

   stage 'Stage 4 -execution'
   sh 'java -jar $JENKINS_HOME/workspace/helloWorld/target/test-1.0.jar'
}