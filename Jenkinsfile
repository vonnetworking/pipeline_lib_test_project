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
        MPLPipelineV2 {}
    }
}
