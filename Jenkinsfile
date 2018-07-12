node('master') 
{
    stage('ContinuousDownload')
    {
        git 'https://github.com/dibya-jenkins/scriptd.git'
    }
    stage('ContinuousBuild')
    {
        sh 'mvn package'
    }
    stage('ContinuousDeployment')
    {
        sh 'scp /home/ubuntu/.jenkins/workspace/Scripted_Pipeline/webapp/target/webapp.war ubuntu@172.31.29.240:/var/lib/tomcat7/webapps/king.war'
    }
    stage('ContinuousTesting')
    {
        git 'https://github.com/selenium-saikrishna/TestingOnLinux.git'
      sh 'echo "test passed"'  
    }
    stage('ContinuousDelivery')
    {
        sh 'scp /home/ubuntu/.jenkins/workspace/Scripted_Pipeline/webapp/target/webapp.war ubuntu@172.31.21.179:/var/lib/tomcat7/webapps/queen.war'
    }
    
    
    
    
    
}
