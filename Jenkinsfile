
node {
  // Mark the code checkout 'stage'....
		stage 'Stage Checkout master'

  // Checkout code from repository and update any submodules
  checkout changelog: false, poll: false, \
	              scm: [$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: \
	                 [[$class: 'ScmName', name: 'gradle']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'Database', \
	                 url: 'https://github.com/yeshwanthreddy77/jenkins-example.git']]]
  checkout changelog: false, poll: false, \
	              scm: [$class: 'GitSCM', branches: [[name: '*/develop']], doGenerateSubmoduleConfigurations: false, extensions: \
	                 [[$class: 'ScmName', name: 'gradle']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'Database', \
	                 url: 'https://github.com/yeshwanthreddy77/jenkins-example.git']]]
		
  
		stage 'Master stage- test'  
        if (env.BRANCH_NAME == 'master') {
            echo 'I only execute on the master branch'
        } else {
            echo 'I execute elsewhere'
        }
		stage 'Stage Checkout develop'
  checkout changelog: false, poll: false, \
	              scm: [$class: 'GitSCM', branches: [[name: '*/develop']], doGenerateSubmoduleConfigurations: false, extensions: \
	                 [[$class: 'ScmName', name: 'gradle']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'Database', \
	                 url: 'https://github.com/yeshwanthreddy77/jenkins-example.git']]]
    
		stage 'Stage Build develop'
	if (env.BRANCH_NAME == 'develop') {
            echo 'I only execute on the develop branch'
        } else {
            echo 'I execute elsewhere'
        

  //branch name from Jenkins environment variables
  echo "My branch is: ${env.BRANCH_NAME}"
		}
}

