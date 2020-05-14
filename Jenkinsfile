node {
            stage('clean-up'){
                    deleteDir()
                    echo 'Delete folders'
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
            stage('Post clean-up'){
                    deleteDir()
                    echo 'Delete folders'
            }
}
