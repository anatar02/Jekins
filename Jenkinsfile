pipeline { 
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') { 
            steps { 
			
            }
        }
        stage('Test'){
            steps {
			   }
        }
        stage('Deploy') {
            steps {
               cucumber failedFeaturesNumber: -1, failedScenariosNumber: -1, failedStepsNumber: -1, fileIncludePattern: '**/*.json', pendingStepsNumber: -1, skippedStepsNumber: -1, sortingMethod: 'ALPHABETICAL', undefinedStepsNumber: -1
            }
        }
		stage('Email'){
		steps{
		echo 'Build Success'
		}
		
	}
}
}