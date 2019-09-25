pipeline {
    agent any
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
stages {
        stage('Input-from-Parameters') {  
            steps {
                echo "Hello ${params.PERSON} and ${env.NODE_NAME}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
            }
        } 
   stage ('Checkout Code'){
    steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Rashid-kashmiri/nvnshoppingcart.git']]])
    }
	}
    
    stage ('***COMPILE THE CODE***'){
	steps {
        sh 'mvn clean compile'
	}
    }
		
    stage ('***First TEST THE CODE***'){
	steps{
        sh 'mvn test'	
	}
    }
     
   stage ('***PACKAGE THE CODE***'){
	steps{
        sh "mvn package"
	}	
   }
        
    stage ('***Deploy to Nexus***'){
        //sh 'rm /var/lib/tomcat/webapps/nvnshoppingcart*'
      steps{
        sh 'sudo cp **/*.war /opt/Jenkins/'	
	}	
        
    }
	   
}

		
}

