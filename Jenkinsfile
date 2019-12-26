node {
    stage ("Checkout") {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/vonnetworking/pipeline_lib_test_project.git']]])
    }
    stage ("Setup Env") {
        script {
            envFileContents = readFile("${WORKSPACE}/manifest.yaml")
            config = readYaml file: "${WORKSPACE}/manifest.yaml"
            echo "Pipeline Version: " + config.pipeline_version
            echo "initializing MD pipeline common lib version " + config.pipeline_version
        }
        library 'MDPipeline@' + config.pipeline_version
    }
    MPLPipelineV2 {}
}
