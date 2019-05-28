node('master') 
{
   stage('continuousdownload') 
   {
   git 'https://github.com/desamsett/dev.git'
}
stage('continuousbuild')
{
    sh label: '', script: 'mvn package'
}
stage('continuousdeploy')
{
input message: 'Approval from prod team', submitter: 'admin'
sh label: '', script: 'scp "/home/ubuntu/.jenkins/workspace/scripted pipeline/webapp/target/webapp.war" ubuntu@172.31.4.225:/home/ubuntu/apache-tomcat-8.5.41/webapps'
}
}
