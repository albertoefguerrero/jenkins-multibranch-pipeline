pipeline {
    agent any
    stages {
        stage('First') {
	        steps {
	   	        script {
		            env.EXECUTE='True'
		        }
                sh 'echo "Step One"'
		    }     
		}
        stage('Second') {
            when {
                environment name: 'EXECUTE', value: 'True'
            }
		    steps {
	   	        sh 'echo "Updating Second Stage"'    
		    }
		} 
	    stage('Third') {
            when {
                environment name: 'EXECUTE', value: 'False'
            }
	        steps {
		        sh 'echo "Step Three"'
                sleep(1)
		    }
		}
	}
}

