pipeline{
 
 tools{
 
 maven 'local_maven'
 }
 
 agent any
 
 stages{
 stage ('Clone a repo')
 {
 steps {
 git 'https://github.com/ireep/zenbook-devop.git'
 }
 }
 
 stage ('Package the code')
 {
 steps{
 sh 'mvn package'
 }
 }
 
 stage ('Deploy the code')
 {
 steps{
 deploy adapters: [tomcat9(credentialsId: 'tomcat-id', path: '', url: 
'http://localhost:9090/')], contextPath: null, war: '**/*.war'
 }
 }
 
 }
}
