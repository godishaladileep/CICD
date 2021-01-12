pipeline {
	    agent any
	

	        // Environment Variables
	        environment {
	        MAJOR = '1'
	        MINOR = '0'
	        //Orchestrator Services
	        UIPATH_ORCH_URL = "https://cloud.uipath.com/"
	        UIPATH_ORCH_LOGICAL_NAME = "kanerpsmiups"
	        UIPATH_ORCH_TENANT_NAME = "DefaultTenant"
	        UIPATH_ORCH_FOLDER_NAME = "Default"
	    	}
	
	    stages {
	  
	         // Build Stages
	        stage('Build') {
	            steps {
	                echo "Building..with ${WORKSPACE}"
					UiPathPack( credentials: Token(accountName: 'kanerpsmiups', credentialsId: '3f48592b-8043-4600-8702-70c4bcd8ed29'), 
							orchestratorAddress: 'https://cloud.uipath.com/', 
							orchestratorTenant: 'DefaultTenant', 
							outputPath: '${WORKSPACE}\\Outputa', 
							projectJsonPath: 'project.json', 
							useOrchestrator: true, 
							version: AutoVersion()
						  )
	            }
	        }
			
			 // Deploy Stages
	        stage('Deploy') {
	            steps {
	                echo "Deploying..with ${WORKSPACE}"
	            }
	        }
	    }
}
