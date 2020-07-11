 

pipeline {
    agent any

    
    stages {
		stage('Checkut') 
		{
            steps {
              git branch: "master", url: "https://github.com/rajagitcommits/cicd-pipeline-train-schedule-jenkins.git" 

            }
        }

        stage('Build') 
		{
            steps {
                sh './gradlew build --no-daemon'
            }
        }
    }
	
	 post { 
		 success
		 {
			archiveArtifacts 'dist/*.zip'
		 }
        always { 
            echo 'Build succeeded and artifact archived'
        }
    }
}
