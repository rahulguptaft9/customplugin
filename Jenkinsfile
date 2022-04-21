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
  stage("Build") {
      steps {
        sh "mvn  compile pom.xml"
        }
    }

  
  
  }
}
