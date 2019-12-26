pipeline {
    agent any
    stages {
        stage ("Checkout") {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/vonnetworking/pipeline_lib_test_project.git']]])
            }
        }
        stage ("Setup Env") {
            steps {
                script {
                    envFileContents = readFile("${WORKSPACE}/manifest.yaml")
                    config = readYaml file: "${WORKSPACE}/manifest.yaml"
                    echo "Pipeline Version: " + config.pipeline_version
                    echo "initializing MD pipeline common lib version " + config.pipeline_version
                }
                library 'MDPipeline@' + config.pipeline_version
            }
        }
        stage ("Init") {
            steps {
                echo ""
            }
        }
    }
}
/*MPLPipeline {
    git_url = "https://github.com/vonnetworking/pipeline_lib_test_project.git"
    // git.branch
    // git.project_name
    // git.project_key
   build_tool = 'gradle'
   // Gradle
   tool_version = 6
   tasks = 'build'
   // Maven (default: Maven 3)
   // maven.goals = 'clean install'
   // maven_goals = 'clean install test'
}*/
