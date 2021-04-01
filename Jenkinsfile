pipeline {
    agent any

    stages {

        stage('Verify branch') {
            steps {
               echo "$GIT_BRANCH"
            }
        }

        stage('Docker Build') {
            steps {
            //sh "/usr/local/bin/pwsh -Command \"Get-Host | Select-Object Version\""
            pwsh(script: 'docker images -a')
            pwsh(script: """
               cd azure-vote/
               docker images -a
               docker build -t jenkins-pipeline .
               cd ..
            """)
         }
      }   





        
    }
}
