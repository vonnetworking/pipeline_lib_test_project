@Library('mpl') _
stage ('check this out') {
   steps {
      step {
         sh ''' echo HELLO WORLD!  - I JUST OVERRODE THE PIPELINE'''
      }
   }
}
MPLPipeline {
   /*
    * Checkout
    */
    git_url = "https://github.com/vonnetworking/pipeline_lib_test_project.git"
    // git.branch
    // git.project_name
    // git.project_key
  /*
   * Build
   */
   build_tool = 'gradle'
   // Gradle
   tool_version = 6
   tasks = 'build'
   // Maven (default: Maven 3)
   // maven.goals = 'clean install'
   // maven_goals = 'clean install test'
}
