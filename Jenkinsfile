
node {
  // Mark the code checkout 'stage'....
  stage 'Stage Checkout'

  // Checkout code from repository and update any submodules
  checkout scm
  
  stage 'Stage Build'

  //branch name from Jenkins environment variables
  echo "My branch is: ${env.BRANCH_NAME}"

  def flavor = flavor(env.BRANCH_NAME)
  echo "Building flavor ${flavor}"

  

// Pulls the android flavor out of the branch name the branch is prepended with /QA_
//@NonCPS
//def flavor(branchName) {
  //def matcher = (env.BRANCH_NAME = 'master')
  //assert matcher.matches()
  //matcher[0][1]
//}
