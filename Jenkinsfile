node('built-in') 
{
   stage('ContinousDownload') 
   {
        git 'https://github.com/ganesh310396/maven.git'
   }
    stage('ContinousBuild') 
   {
        sh 'mvn package'
   }
    stage('ContinousDeployment') 
   {
       deploy adapters: [tomcat9(credentialsId: '1a3c8220-b9cb-4b77-a23f-7ef9d06764a2', path: '', url: 'http://172.31.32.41:8080')], contextPath: 'testapp', war: '**/*.war'
   }
   stage('ContinousTesting') 
   {
       git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
   }
}
