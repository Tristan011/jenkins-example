node {
            stage('Node locatie aanpassen'){
		sh 'sudo cp -R /var/lib/jenkins/workspace/SNB2_Keuze/* /var/lib/jenkins/workspace/SNB2_Keuze@2/'
	   }
            stage('Build'){
                
                    withMaven{ //hiervoor moet plugin 'pipeline-maven' geinstalleer worden
                       sh 'mvn clean compile'
                    
                }
            }
            stage('Test'){
                
                    withMaven{ //hiervoor moet plugin 'pipeline-maven' geinstalleer worden
                        sh 'mvn test'
                    
                }
            }
            stage('Artifact'){
                
                    archiveArtifacts artifacts: '**', onlyIfSuccessful: true
                
            }
            stage('Deployment stage'){
                        sh 'cd target/classes/com/techprimers/testing/ java FizzBuzz'
            }
            
}
