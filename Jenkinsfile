node{

 def mavenHome = tool name: "maven"
 
       echo "GitHub BranhName ${env.BRANCH_NAME}"
       echo "Jenkins Job Number ${env.BUILD_NUMBER}"
       echo "Jenkins Node Name ${env.NODE_NAME}"
  
       echo "Jenkins Home ${env.JENKINS_HOME}"
       echo "Jenkins URL ${env.JENKINS_URL}"
       echo "JOB Name ${env.JOB_NAME}"

 stage('CheckOutCode')
 {
git credentialsId: '2477c8c7-b215-4869-8e80-b4b6228d7489', url: 'https://github.com/bhanubanu36/maven_web_application.git'
 
 stage('Build')
 {
  bat "${mavenHome}/bin/mvn clean package"
 }

 stage('SonarQubeReport'){
 bat "${mavenHome}/bin/mvn clean sonar:sonar"
 }
 
 
 stage('UploadArtifactIntoNexus'){
 bat "${mavenHome}/bin/mvn clean deploy"
 }
 
 
 }
 
 
}
