pipeline {
	
agent any
	
node {
    def dateFormat = new SimpleDateFormat("yyyyMMddHHmm")
    def date = new Date()

    println(dateFormat.format(date))
}
	
  // options { timestamps () }
		
stages {	
	stage ('Checkout Code'){	
		steps {	
		     
		     checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Rashid-kashmiri/DevOpsClassCodes.git']]])
		       }
		     }
	stage ('BuildIn'){		
		steps {				
			sh 'mvn clean compile'
			sh 'mvn test'
			sh "mvn package"			
		}			
	}
	
	stage('ArchiveArtifacts'){
            steps {                
                archiveArtifacts artifacts: '**/target/*.war', fingerprint: true , onlyIfSuccessful: true		   
            }
        }
    }
}   
	  	
	

