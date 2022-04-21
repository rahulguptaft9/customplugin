pipeline {
  agent any
  tools {
    maven 'MAVEN_HOME-3.6.3'
  }
  
  stages{
    
  stage('Git') {
		steps{
		git 'https://github.com/rahulguptaft9/customplugin'
		}	
	}  
  /*stage("Build") {
      steps {
        sh "mvn  compile pom.xml"
        }
    }*/
	  
stage('SonarQube'){
		tools{
		jdk "jdk11"
		}
		steps{
		script {
          	scannerHome = tool 'sonar_coverage';
        	}
		withSonarQubeEnv('sonar_coverage'){
		sh '''
		/var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/sonar_coverage/bin/sonar-scanner \
		 mvn clean verify sonar:sonar \
		-Dsonar.host.url=http://192.168.122.141:9004/sonarqube \
		-Dsonar.login=12033d0d90fd6250956a2ab149862bbe7e0effef \
		-Dsonar.projectKey=javajava \
		-Dsonar.projectName=javajava
		'''

		}		
		}
	
	}	  
	  
	  

  
  
  }
}
