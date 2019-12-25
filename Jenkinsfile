@Library('mpl') _
pipeline {
    agent any

    stages {
        stage('Look at me doing stuff I want to do, and not what you are supposed to be making me do!!') {
            steps {
                echo 'Delete all the stuffs and pass all scans!!'
            }
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
