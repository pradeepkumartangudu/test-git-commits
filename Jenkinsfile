pipeline { 
    agent any 
    stages {
	     stage('Build & Deploy') { 
            steps { 
                sshagent( credentials: [ 'some_creds' ] ) {
      checkout scm
      def lastSuccessfulCommit = getLastSuccessfulCommit()
      def currentCommit = commitHashForBuild( currentBuild.rawBuild )
      if (lastSuccessfulCommit) {
        commits = sh(
          script: "git rev-list $currentCommit \"^$lastSuccessfulCommit\"",
          returnStdout: true
        ).split('\n')
        println "Commits are: $commits"
      }
    }
            }
        }
    }
}
