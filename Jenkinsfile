pipeline { 
    agent { label 'Slave1-USA' }
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
				sh label: '', script: '''setJAVA_HOME=C:\\Java\\jdk8\\jre
	set PATH=${JAVA_HOME}/bin:${PATH}

		set M2_HOME=C:\\dev\\tools\\maven
set PATH=${M2_HOME}/bin:${PATH}

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
		stage('Email'){
		steps{
		echo 'Build Success'
		}
		stage('Email'){
		steps{
		echo 'Build Success'
		}
		stage('Email'){
		steps{
		echo 'Build Success'
		}
		stage('Email'){
		steps{
		echo 'Build Success'
		}
		stage('Email'){
		steps{
		echo 'Build Success'
		}
		stage('Email'){
		steps{
		echo 'Build Success'
		}
		stage('Email'){
		steps{
		echo 'Build Success'
		}
		stage('Email'){
		steps{
		echo 'Build Success'
		}
		stage('Email'){
		steps{
		echo 'Build Success'
		}
		stage('Email'){
		steps{
		echo 'Build Success'
		}
		stage('Email'){
		steps{
		echo 'Build Success'
		}
		stage('Email'){
		steps{
		echo 'Build Success'
		}
		stage('Email'){
		steps{
		echo 'Build Success'
		}
		stage('Email'){
		steps{
		echo 'Build Success'
		}
	}
}
}