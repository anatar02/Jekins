pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
	
	  try {
	  
    stages {
        stage('Build') { 
            steps { 
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'Credential', url: 'https://Ashok.Natarajan%40fepoc.com@bitbucket/scm/ta/dx-bdd.git']]])
            }
        }
        stage('Test'){
            steps {
				sh label: '', script: '''setJAVA_HOME=C:\\Java\\jdk8\\jre
	set PATH=${JAVA_HOME}/bin:${PATH}

		set M2_HOME=C:\\dev\\tools\\maven
set PATH=${M2_HOME}/bin:${PATH}
# mvn test  -DEnv=W2 -DBrowser=firefox -Dtest=EnrollmentRunner test
# mvn test -Dcucumber.options="src/test/resources/featureFiles/ProcessNewClaim.feature" -Dcucumber.options="–tags @newContract"
mvn test  -DEnv=W2 -DBrowser=firefox  -DRUNNER_TYPE=EnrollmentRunner -Dcucumber.options="--tags @newContract" '''
            }
        }
        stage('Deploy') {
            steps {
               cucumber failedFeaturesNumber: -1, failedScenariosNumber: -1, failedStepsNumber: -1, fileIncludePattern: '**/*.json', pendingStepsNumber: -1, skippedStepsNumber: -1, sortingMethod: 'ALPHABETICAL', undefinedStepsNumber: -1
            }
        }
		stage('Email'){
		steps{
		commitChangeset = sh(returnStdout: true, script: 'git diff-tree --no-commit-id --name-status -r HEAD').trim()
			}
	}
	}
	 catch (err) {

        currentBuild.result = "FAILURE"

            mail body: "project build error is here: ${env.BUILD_URL}" ,
            from: 'xxxx@yyyy.com',
            replyTo: 'yyyy@yyyy.com',
            subject: 'project build failed',
            to: 'zzzz@yyyyy.com'

        throw err
    }

}