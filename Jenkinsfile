
node()
{
    stage "Checkout Code"
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Rashid-kashmiri/nvnshoppingcart.git']]])
    
    stage "***COMPILE THE CODE***"
        sh "mvn clean compile"
		
    stage "***First TEST THE CODE***"
        sh "mvn test"	
    
    stage "*******Second TEST THE CODE*******"
        sh "mvn test"	
		
    stage "***PACKAGE THE CODE***"
        sh "mvn package"	
        
    stage "***Deploy Application***"
        //sh 'rm /var/lib/tomcat/webapps/nvnshoppingcart*'
        sh 'sudo cp **/*.war /opt/Jenkins/'		
}
