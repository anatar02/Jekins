pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') { 
            steps { 
               
			   checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'ca620896-7d7e-423d-8126-e3a25249db11', url: 'https://github.com/anatar02/CucumberJVMExamples.git']]])
            }
        }
        stage('Test'){
            steps {
				sh label: '', script: '''setJAVA_HOME=C:\\Java\\jdk8\\jre
				set PATH=${JAVA_HOME}/bin:${PATH}

				set M2_HOME=C:\\dev\\tools\\maven
				set PATH=${M2_HOME}/bin:${PATH}
				
				mvn test
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