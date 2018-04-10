
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

  stage 'Stage Archive'
  //tell Jenkins to archive the apks
  archiveArtifacts artifacts: 'app/build/outputs/apk/*.apk', fingerprint: true

  stage 'Stage Upload To Fabric'
  sh "./gradlew crashlyticsUploadDistribution${flavor}Debug  -PBUILD_NUMBER=${env.BUILD_NUMBER}"
}

// Pulls the android flavor out of the branch name the branch is prepended with /QA_
@NonCPS
def flavor(branchName) {
  def matcher = (env.BRANCH_NAME =~ ([a-z_]+)/)
  assert matcher.matches()
  matcher[0][1]
}
