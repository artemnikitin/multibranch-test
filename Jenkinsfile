pipeline {

    agent {
        label 'ubuntu'
    }

    parameters {
        choice(name: 'API_TESTS_ENV', choices: ['qa', 'staging', 'production'])
        string(name: 'API_TESTS_REGION', defaultValue: '')
        booleanParam(name: 'API_TESTS_BOOST_CLUSTERS', defaultValue: false)

    }

    options {
        timeout(time: 15, unit: 'MINUTES')
    }

    stages {
        stage('Run build') {
            steps {
                echo "API_TESTS_ENV: " + params.API_TESTS_ENV
                echo "API_TESTS_REGION: " + params.API_TESTS_REGION
                echo "API_TESTS_BOOST_CLUSTERS: " + params.API_TESTS_BOOST_CLUSTERS

                sh "printenv"
            }
        }
    }

    post {
        cleanup {
            cleanWs()
        }
    }

}
