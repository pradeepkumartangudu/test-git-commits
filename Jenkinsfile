pipeline { 
    agent any 
    stages {
	     stage('Build & Deploy') { 
            def lastSuccessfulCommit = getLastSuccessfulCommit()
            }
        }
    }
def getLastSuccessfulCommit() {
  def lastSuccessfulHash = null
  def lastSuccessfulBuild = currentBuild.rawBuild.getPreviousSuccessfulBuild()
  if ( lastSuccessfulBuild ) {
    lastSuccessfulHash = commitHashForBuild(lastSuccessfulBuild)
  }
  return lastSuccessfulHash
}
}
